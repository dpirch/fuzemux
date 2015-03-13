This is very simple Windows Batch file for encoding videos. Download [MPlayer](http://www.mplayerhq.hu) (which includes mencoder) and fuzemux. Create the batch file (a text file called fuze-encode.bat or whatever) with the following content somewhere, set the correct paths to the two executables, and then you can just drag video files on the batch file to convert them.

```
@echo off
set MENCODER=C:\path\to\mencoder.exe
set FUZEMUX=C:\path\to\fuzemux.exe
set file=%1

ECHO --- RUNNING MENCODER... ---
%MENCODER% -ovc lavc -oac mp3lame -ffourcc DX50 ^
	-ofps 20 -noskiplimit -vf pp=li,expand=:::::224/176,scale=224:176 ^
	-lavcopts vcodec=mpeg4:vqscale=3:vmax_b_frames=0:keyint=15 ^
	-srate 44100 -af resample=44100:0:1,format=s16le ^
	-lameopts cbr:br=128 ^
	-o %file%-tmp.avi %file% -msglevel mencoder=1 

ECHO --- RUNNING FUZEMUX... ---
%FUZEMUX% %file%-tmp.avi %file%-fuze.avi

del %file%-tmp.avi
pause
```