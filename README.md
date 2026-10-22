## how to use
use regex search to find what you are looking for \
each 'entry' has a description and keywords 

### replace words in all files
replace change word content
```bash
find . -name "*.fileExtension" -exec sed -i 's/old/new/' {} \;
```

### convert all flacs to 320kb/s mp3
convert transcode audio flac mp3
```bash
mkdir mp3; find . -name "*.flac" -exec ffmpeg -i {} -ab 320k mp3/{}.mp3 \;; cp *.mp3 mp3/; for file in mp3/*; do mv "$file" "${file//.flac/}";done; echo "delete flac and replace with mp3? press enter to continue"; read; rm *.flac; mv mp3/* .; rm -rf mp3/
```

### add gain to mp3 or flac files
gain volume audio mp3 flac
```bash
find . -name "*.mp3" -exec mp3gain -e {} \;
```
```bash
find . -name "*.flac" -exec metaflac --add-replay-gain {} \;
```
