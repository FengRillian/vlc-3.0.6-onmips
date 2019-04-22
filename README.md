vlc-3.0.6-onmips README.md.
vld-3.0.6 package can be got from https://github.com/videolan/vlc .
This document is for vlc compile on Loongson platform.

####Environment Prepare .
1. pkg-config 0.29.2
Download from: https://pkg-config.freedesktop.org/releases/
./configure --build=mips64el-redhat-linux --with-internal-glib
Compile and install.

2. automake tools
automake 1.15
libtool 2.4.5
autoconf 2.69
Download from: http://mirrors.nju.edu.cn/gnu/
Compile and install.

3. Python3.5
https://www.python.org/ftp/python/2.7.10/Python-2.7.10.tar.xz
python 3.5.0
./configure --build=mips64el-redhat-linux
make
sudo make install
Make sure that /usr/bin/python link to python3.5

4. meson
meson-0.47.0
pip3 install --user meson

5. libpthread-stubs
download from: https://xcb.freedesktop.org/dist/
configure and make install 

####Start_compile third party softwares .
cd vlc-3.0.6/contrib/
mkdir native
cd native
../bootstrap
make

While libplacebo compile have error:
./contrib/native/libplacebo/Makefile
add -std=c11

####Compile vlc-3.0.6 .
./configure --enable-ogg --enable-matroska --enable-wma-fixed --enable-mpg123 --enable-merge-ffmpeg --enable-aom --enable-dav1d --enable-vpx --enable-twolame --enable-a52 --enable-dca --enable-libmpeg2 --enable-vorbis --enable-tremor --enable-speex --enable-opus --enable-spatialaudio --enable-theora --enable-oggspots --enable-x265 --enable-x264 --prefix=/home/**/install_dir/
make

