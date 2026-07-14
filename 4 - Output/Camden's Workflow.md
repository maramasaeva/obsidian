# Camden's Workflow

Video edit pipeline for `camden.mp4` — dark, glitchy, anime, noisy, atmospheric rooftop footage from Lighthaven.

---

## Source

- **Input**: `~/Downloads/camden.mp4` — 26.5s, 1280x720 (portrait with -90° rotation → 720x1280), 30fps, h264
- **Audio**: `~/Downloads/4m (2).wav` — 51s, 44100Hz stereo PCM

## 1. Time Manipulation

Split the video into two intermediate files, then concat with a reversed copy.

### Forward part (25.5s normal + 3s slowdown)

```bash
ffmpeg -i camden.mp4 -filter_complex "
[0:v]split=2[main][end];
[main]trim=0:25.5,setpts=PTS-STARTPTS[part1];
[end]trim=start=25.5,setpts=3*(PTS-STARTPTS)[part2];
[part1][part2]concat=n=2:v=1:a=0[out]
" -map "[out]" -an -c:v libx264 -preset medium -crf 18 -pix_fmt yuv420p -y forward.mp4
```

- Last 1 second slowed 3x → 30 frames stretched over 3 seconds
- No frame interpolation (the slight choppiness fits the glitch vibe)

### Reverse part (26.5s at normal speed, reversed)

```bash
ffmpeg -i camden.mp4 -vf "reverse,trim=start=0.0333,setpts=PTS-STARTPTS" \
  -an -c:v libx264 -preset medium -crf 18 -pix_fmt yuv420p -y reverse.mp4
```

- `trim=start=0.0333` skips first frame to avoid duplicate at the pingpong junction
- Reverse plays at normal speed (no slowdown in reverse portion)

### Result

- Forward: 28.5s (25.5 + 3)
- Reverse: ~26.4s
- Total: ~54.9s

## 2. Color Grade & Filters

Applied during final concat. Settled on subtle — preserves the sunset warmth.

```
eq=contrast=0.85:saturation=0.5:brightness=0.03:gamma=0.95,
noise=alls=15:allf=t,
unsharp=5:5:0.8:5:5:0.0
```

| Parameter | Value | Notes |
|-----------|-------|-------|
| contrast | 0.85 | slight reduction, keeps sunset visible |
| saturation | 0.5 | halved, desaturated but not monochrome |
| brightness | 0.03 | tiny bump to stay close to original |
| gamma | 0.95 | slightly darker shadows |
| noise | 15, temporal | light film grain (inflates file size) |
| unsharp | 5:5:0.8 | soft sharpen for subtle edge definition |

### Rejected variations

- **Digital Decay** (A): too extreme, killed the sunset, blue overlay
- **Ghost Signal** (B): too blue/teal, too hazy
- **Anime Noir** (C): good darkness but too purple
- **Corrupted Memory** (D): full magenta RGB split, too aggressive

## 3. Image Overlays

18 images from `~/Downloads/best images/` scattered chaotically across the video.

### Rules

- No images in the first second
- Each image visible for ~1.3-1.5 seconds
- Some temporal overlaps (2 images visible at once)
- Images stay on edges/corners/top/bottom — **never overlay the center zone where people are** (roughly x=150-550, y=300-600)
- Sizes: 310-380px wide, scaled proportionally

### Image picks & timing

| # | Image | Time | Position | Size |
|---|-------|------|----------|------|
| 1 | `download.jpg` (winged angel glitch) | 1.4–2.8s | x=400, y=0 (top-right) | 370 |
| 2 | `download (6).jpg` (anime fractured sky) | 3.2–4.5s | x=-40, y=70 (left edge, top) | 340 |
| 3 | `binary building.jpg` (BSOD demolition) | 4.0–5.3s | x=250, y=700 (center-bottom) | 320 |
| 4 | `download (5).jpg` (glitch apartments) | 7.2–8.5s | x=420, y=20 (top-right bleed) | 360 |
| 5 | `download (3).jpg` (knight archer HUD) | 9.8–11.2s | x=-50, y=750 (left-bottom bleed) | 370 |
| 6 | `download (10).jpg` (train station ghost) | 12.5–13.7s | x=310, y=80 (right-top) | 330 |
| 7 | `download (13).jpg` (Gundam collage) | 15.0–16.4s | x=80, y=760 (left-bottom) | 350 |
| 8 | `Fork.jpg` (icy surreal) | 16.0–17.3s | x=420, y=0 (top-right, overlaps #7) | 340 |
| 9 | `download (16).jpg` (blue glitch humans) | 19.8–21.2s | x=-30, y=30 (left-top) | 360 |
| 10 | `download (11).jpg` (terminal mecha) | 23.0–24.4s | x=-40, y=880 (bottom-left bleed) | 330 |
| 11 | `download (1).jpg` (HK alley green glow) | 25.5–26.8s | x=430, y=40 (right-top bleed) | 310 |
| 12 | `download (24).jpg` (crushing weight) | 28.5–30.0s | x=50, y=850 (bottom-left) | 370 |
| 13 | `𝗶𝗿𝟯𝗺.jpg` (anime smoking night) | 32.0–33.3s | x=410, y=830 (bottom-right) | 340 |
| 14 | `download (25).jpg` (dark 3D spider world) | 35.0–36.5s | x=-40, y=90 (left-top bleed) | 380 |
| 15 | `will you save me.jpg` (blue/green glitch) | 38.5–39.8s | x=190, y=900 (bottom-center) | 330 |
| 16 | `download (8).jpg` (PEOPLE diagram) | 41.5–43.0s | x=420, y=10 (top-right) | 350 |
| 17 | `download (12).jpg` (power line glitch) | 45.5–47.0s | x=-30, y=0 (left-top bleed) | 360 |
| 18 | `тгк_ волнение истомы.jpg` (THE END) | 49.5–51.0s | x=90, y=850 (bottom-left) | 370 |

## 4. Final Render Command

Single-pass: concat + filters + audio + all 18 overlays.

```bash
ffmpeg \
  -i forward.mp4 \
  -i reverse.mp4 \
  -i "4m (2).wav" \
  -i [18 image inputs...] \
  -filter_complex "
    [0:v][1:v]concat=n=2:v=1:a=0,
    eq=contrast=0.85:saturation=0.5:brightness=0.03:gamma=0.95,
    noise=alls=15:allf=t,
    unsharp=5:5:0.8:5:5:0.0[base];
    [2:a]apad=whole_dur=55[aout];
    [scale each image]...
    [chain 18 overlay filters with enable='between(t,start,end)']...
  " -map "[vout]" -map "[aout]" \
  -c:v libx264 -preset medium -crf 26 -pix_fmt yuv420p \
  -c:a aac -b:a 192k -shortest -movflags +faststart \
  -y camden_edit.mp4
```

### Output

- **Duration**: 54.9s
- **Size**: ~182MB (grain inflates this — `-tune grain` made it worse, not better)
- **Resolution**: 720x1280 portrait

## Notes

- `noise` filter destroys temporal redundancy → big file sizes. CRF 26 was the sweet spot between quality and size.
- `-tune grain` counterintuitively increased bitrate. Dropped it.
- Audio (51s) is shorter than video (55s) — last ~4s are silent. `apad` fills with silence.
- Can't write output to same file as input in ffmpeg — use temp file then `mv`.
- Build forward/reverse intermediates in parallel for speed.
