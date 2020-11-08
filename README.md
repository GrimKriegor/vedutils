# vedutils

Simple video editing utilities.

Just a bunch of wrappers for [FFmpeg](https://ffmpeg.org/) that help me edit video super fast and without unnecessary re-encoding.

They are great for editing massive video files on an old laptop and for automation.


## Overview


### vedclip

Snip clips out of videos

```
vedclip input_file start_time end_time [output_file]
```

 Example:

```
vedclip boring_2h_marathon.mkv 1:24:32 1:24:56 poggers_frag_clip.mkv
```


### vedclipmulti

Snip multiple clips out of a video in one go

```
vedclipmulti input_file [(start_time end_time)...]
```

 Example:

```
vedclipmulti ds3_4h_invasion.mkv 1:25 2:43 6:01 8:23 10:16
```


### vedcat

Concatenate videos

```
vedcat [video_file...]
```

 Example:

```
vedcat intro.mkv content.mkv advertisement.mkv outro.mkv
```

### vedamix

Mix an audio track into an audio/video file

```
vedamix video_file audio_file begining [ending] [audio_volume_percent] [output_file]
```

 Example:

```
vedamix cool_frag_vid.mkv awesome_soundtrack.ogg 0:32 5:45 80 cool_frag_vid_with_music.mkv
```


### vedbdt

Detect and output black frame transition timestamps

```
vedbdt video_file
```

Example:

```
vedclipmulti 8h_invasion_stream.mkv $(vedbdt 8h_invasion_stream.mkv)
```


## Workflow

The following example demonstrates how to take in a huge hours long video file, pick the best parts, add music and join them all together in a single video file, in only a few minutes, without costly re-encoding.


Slice huge video into individual sessions, by detecting black frame transitions

```
vedclipmulti huge_12h_session.mkv $(vedbdt huge_12h_session.mkv)
```


Add an epic soundtrack to one of the sessions

```
vedamix invasion8.mkv ebic_song.ogg 0:21 4:33 100 invasion8-ebic.mkv
```


Trim a needlessly large video

```
vedclip testsession2.mkv 23:30 1:11:15 testsession2-trimed.mkv
```


Join favourite clips into a single video file

```
vedcat invasion{2..5}.mkv invasion8-ebic.mkv testsession2-trimed.mkv boss-fight.mkv
```
