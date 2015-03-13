To create video files for the Sansa Fuze (without using the official the official "Sansa Media Converter", which is Windows-only, produces files with bad A/V sync, and is a bit annoying),  the video has to be transcoded to mpeg-4 part 2 video and mp3 audio, with specific codec settings, frame rate, resolution etc., see [this thread](http://forums.sandisk.com/sansa/board/message?board.id=sansafuse&view=by_date_ascending&message.id=31762#M31762) on the Sandisk forum for details. This can be done using ffmpeg or mencoder. However the Fuze also requires a very specific structure for the AVI container format and cannot play the AVI files created using mencoder or most other video encoders. Although remuxing them using the [AVI-Mux GUI](http://www.alexander-noe.com/video/amg/) application creates playable files, the Fuze still has some problems with these files and sometimes crashes during seeking.

The purpose of fuzemux is therefore to remux avi files into the exact container format required for playing them on the Fuze.

## Installing and Using Fuzemux ##
See [Installing](Installing.md) for how to install Fuzemux. To use Fuzemux, just jun
`fuzemux inputfile.avi outputfile.avi` on the command line.

Since fuzemux handles only a part of to process to convert any source video to a file playable on the Fuze, the input file must already be reencoded, for example using mencoder. MencoderBatchFile is a very simple batch file for Windows that does this and remuxes the video using fuzemux afterwards.

Alternatively, you might want to use one of the following projects that also use both mencoder and fuzemux:
  * video4fuze: [forum thread](http://forums.sandisk.com/sansa/board/message?board.id=sansafuse&thread.id=40256) / [project home page](http://code.google.com/p/video4fuze/)
  * FuzeVidz: [forum thread](http://forums.sandisk.com/sansa/board/message?board.id=sansafuse&thread.id=39242)

There is a discussion group for fuzemux [here](http://groups.google.com/group/fuzemux-discuss).

Changes between release versions are documented in the [NEWS file](http://fuzemux.googlecode.com/svn/trunk/NEWS).