### Working With Files

*Super tip: You can create an AWS Lambda layer with a static build of ffmpeg and perform these actions from within Lambda*<br>
<br>
*Remove the audio track from an MP4 and save as output.mp4*<br>
ffmpeg -i input.mp4 -an output.mp4<br>
<br>
*Check the internal integrity of video mp4 using ffmpeg*<br>
ffmpeg -v error -i input.mp4 -f null - 2>error.log<br>
<br>
*Extract and save a segment from the middle of an MP4*<br>
ffmpeg -i input.mp4  -ss 0 -t 779 -vcodec copy -acodec copy seg1.mp4<br>
<br>
*Extract all audio and video after the 788 second mark from an MP4*<br>
ffmpeg -i input.mp4  -ss 788 -vcodec copy -acodec copy seg2.mp4<br>
<br>
*Generate an optimized animated gif of the first 10 seconds of a video*<br>
ffmpeg -y -t 10 -i input.mp4 -filter_complex "fps=10,scale=720:-1:flags=lanczos,split[s0][s1];[s0]palettegen=max_colors=50[p];[s1][p]paletteuse=dither=bayer" output.gif<br>
<br>
*Get the duration of a video*<br>
ffmpeg -i out.mp4 2>&1 | grep "Duration"| cut -d ' ' -f 4 | sed s/,// | sed 's@\..*@@g' | awk '{ split($1, A, ":"); split(A[3], B, "."); print 3600*A[1] + 60*A[2] + B[1] }'<br>
<br>
*Take an audio only resource, add a black screen video track to it using loop.jpg as background and save as MP4*<br>
ffmpeg -loop 1 -i loop.jpg -i audio.mp3 -shortest -c:v libx264 -c:a copy final.mp4<br>
<br>
*Convert an audio-only MP4 to MP3 format*<br>
1.5 hour mp3 (200MB) took 1.5 minutes on c5.2xlarge<br>
time  ffmpeg -i input.mp4 -q:a 0 -map a out.mp3<br>
<br>
