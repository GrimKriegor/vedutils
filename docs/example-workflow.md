# Example workflow

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
