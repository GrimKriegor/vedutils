# vedutils

Video editing utilities

Collection of wrappers that abstract some of the complexities of using [FFmpeg](https://ffmpeg.org/)


## Dependencies

- ffmpeg
- bash
- bc


## Overview


### vedclip

Snip clips out of videos

```
vedclip VIDEO_FILE START_TIME [END_TIME] [OUTPUT_FILE]
```

 Example:

```
vedclip boring_2h_marathon.mkv 1:24:32 1:24:56 poggers_frag_clip.mkv
```


### vedclipmulti

Snip multiple clips out of a video in one go

```
vedclipmulti VIDEO_FILE START_TIME [END_TIME] [(START_TIME END_TIME)...]
```

 Example:

```
vedclipmulti ds3_4h_invasion.mkv 1:25 2:43 6:01 8:23 10:16
```


### vedcat

Concatenate videos

```
vedcat VIDEO_FILE VIDEO_FILE [VIDEO_FILE...]
```

 Example:

```
vedcat intro.mkv content.mkv advertisement.mkv outro.mkv
```

### vedamix

Mix an audio track into an audio/video file

```
vedamix VIDEO_FILE AUDIO_FILE BEGINING [ENDING] [AUDIO_VOLUME_PERCENT] [OUTPUT_FILE]
```

 Example:

```
vedamix cool_frag_vid.mkv awesome_soundtrack.ogg 0:32 5:45 80 cool_frag_vid_with_music.mkv
```


### vedbdt

Detect and output black frame transition timestamps

```
vedbdt VIDEO_FILE [MINIMUM_DURATION_IN_SECONDS] [RATIO_OF_BLACK_IN_FRAME]
```

Example:

```
vedclipmulti 8h_invasion_stream.mkv $(vedbdt 8h_invasion_stream.mkv 0.05 1.00)
```


## Configuration

There are a few settings which are tunnable via environment variable

### `VEDUTILS_FFMPEG_ARGS_EXTRA`

Specifies extra arguments to be passed into FFmpeg calls


## Documentation

Check [docs/](docs) for more details
