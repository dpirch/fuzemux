## Windows ##
To install Fuzemux on Windows, get the latest Windows binary package (fuzemux-x.x.x-win32.zip) from the [Downloads](http://code.google.com/p/fuzemux/downloads/list) section, and unzip it somewhere. It contains just the executable.

## Debian/Ubuntu ##
.deb packages are currently not maintained by this project, but are available as part of the video4fuze project: http://code.google.com/p/video4fuze/downloads/list

## Other ##
To use Fuzemux on other operating systems, you need to compile it from source. To compile and install it on a UNIX-like system (or Windows using MSYS), download and untar the source code release, go to its directory and run
```
./configure
make
make install
```

## Using the SVN Version ##
You can also check out the most recent version from the SVN using
```
svn checkout http://fuzemux.googlecode.com/svn/trunk/ fuzemux
```
Before you can compile the SVN version, you have to create the configure script and other necessary files by calling
```
autoreconf --install
```