# video workflow

how to produce short videos for the vault. this is the canonical style — every video gets the same treatment unless stated otherwise.

---

## subtitles

ass format. two base styles:

```
Style: Default,Courier New,38,&H009999FF,&H000000FF,&H00000000,&H78000000,0,0,0,0,100,100,0,0,3,8,0,2,30,30,35,1
Style: Big,Courier New,80,&H009999FF,&H000000FF,&H00000000,&H78000000,0,0,0,0,100,100,0,0,3,8,0,5,30,30,40,1
```

- pink text on transparent black box
- all lowercase
- decorative symbols scattered between phrases: `⋆ ˚｡⋆ ୨୧˚ ✧˖° ˚☆˖° ⋆｡° ✮˖ ⊹⋆`
- Big style for greetings and closings (centered)
- word-level timestamps via `whisper --word_timestamps True`

## foreign-language characters

when a chinese (or other non-latin) term is spoken, its characters appear on screen and stay for the rest of the video.

```
Style: Chinese,PingFang SC,80,&H009999FF,&H000000FF,&H00000000,&H00000000,0,0,0,0,100,100,0,0,1,0,0,7,0,0,0,1
```

- pink, no background, no outline
- positioned in quadrants with `\pos(x,y)` override tags
- Layer 1 (above subtitle Layer 0)
- start time = moment the word is spoken, end time = video end

## M watermark

source file: `4 - Output/assets/m-watermark.mp4`

- ping-pong loop: reverse filter + concat, slowed 2.5x (`setpts=2.5*PTS`)
- recolored to pink (R=255 G=153 B=153) via geq
- dark shadow underneath for visibility (colorchannelmixer → black, gblur sigma=2, offset -2px)
- top-left corner, scaled to 150px wide
- `-stream_loop -1` for infinite loop

## full render command

```bash
ffmpeg -y \
  -i [input video] \
  -stream_loop -1 -i /tmp/m_pingpong.mp4 \
  -filter_complex \
  "[1:v]scale=150:-1,
   curves=all='0/0 0.08/0 0.25/1 1/1',
   format=rgba,
   geq='r=255*clip((r(X,Y)+g(X,Y)+b(X,Y))/300,0,1):
        g=153*clip((r(X,Y)+g(X,Y)+b(X,Y))/300,0,1):
        b=153*clip((r(X,Y)+g(X,Y)+b(X,Y))/300,0,1):
        a=clip((r(X,Y)+g(X,Y)+b(X,Y))/2,0,255)',
   split[mfg][mshadow];
   [mshadow]colorchannelmixer=rr=0:gg=0:bb=0,gblur=sigma=2[shadow];
   [0:v]ass=[subtitle file][sub];
   [sub][shadow]overlay=x=18:y=18:shortest=1[withshadow];
   [withshadow][mfg]overlay=x=20:y=20:shortest=1" \
  -c:v libx264 -preset medium -crf 18 \
  -c:a aac -b:a 128k \
  -shortest [output].mp4
```

## prep steps

1. create ping-pong M loop if not cached: slow original with `setpts=2.5*PTS`, reverse, concat with concat demuxer
2. transcribe with whisper (`--model medium --word_timestamps True`)
3. convert srt to ass, apply styles, lowercase, add symbols
4. add foreign-character dialogue lines if applicable
5. render
6. copy to `4 - Output/Short video's/[title].mp4`
