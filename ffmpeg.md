#### Add an audio track to a video.

`ffmpeg -i thing.mp4 -i audio.mp3 -codec copy -shortest output.mp4`
From [SO](https://stackoverflow.com/questions/11779490/how-to-add-a-new-audio-not-mixing-into-a-video-using-ffmpeg/11783474#11783474)

#### Extract Audio from Video

`ffmpeg -i video.avi -vn -acodec copy audio.mp4`

##### Great for adding audio to gifs
ffmpeg -i video.avi -i audio.mp3 -c:v libx264 -c:a libvorbis -shortest output.mkv
From [SO](https://stackoverflow.com/questions/11779490/how-to-add-a-new-audio-not-mixing-into-a-video-using-ffmpeg/11783474#11783474)
