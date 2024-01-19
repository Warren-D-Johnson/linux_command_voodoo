### Working With Files

*Create a 5GB file containing nulls*<br>
```dd if=/dev/zero of=file.txt count=1024 bs=5048576```<br>
<br>
*Splitting a big binary file into parts (and assembling them again)*<br>
```split -b 10M home.tar.bz2 "home.tar.bz2.part"```<br>
```assemble again: cat home.tar.bz2.parta* > backup.tar.gz.joined```<br>
<br>
*Copy a file to another location on the same server and limit the disk i/o*<br>
```rsync --bwlimit=500k output003.flv temp```<br>
<br>
*List folder contents in one column*<br>
```ls -alt --format=single-column```<br>
<br>
*Find size of each directory and output the directory name and disk usage only*<br>
```find ./ -type d -maxdepth 1 -exec du -h -d 1 {} \;```<br>
<br>
*Pretty-print JSON output from a script*<br>
```./output_some_json.sh | python -m json.tool```<br>
<br>
*sed-based find and replace recursive*<br>
```find ./ -type f -exec sed -i 's/https:\/\/domain\.com/https:\/\/www.domain.com/g' {} +```<br>
<br>
