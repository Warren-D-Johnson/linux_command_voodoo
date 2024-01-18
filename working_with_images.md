### Working With Images

Tip: The mogrify command is part of the ImageMagick software suite.<br>
Super tip: You can create an AWS Lambda layer with a static build of mogrify and perform these actions from within Lambda.<br>
<br>
*Resize all png files to a maximum width of 150 (or 600) and proportionately scale the height*<br>
mogrify -resize 150 \*.png<br>
mogrify -resize 600 \*.png<br>
<br>
*Resample and set quality to 85%*<br>
mogrify -resize 1000 test.jpg<br>
mogrify -quality 85 test.jpg<br>
<br>
*Rotate a PNG 90 degrees counterclockwise*<br>
mogrify -rotate "-90" test.png<br>
<br>
*Change all GIF files to JPG files*<br>
mogrify -format jpeg \*.gif<br>
<br>
<br>