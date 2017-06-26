### OpenCV: Open Source Computer Vision Library

#### Resources

* Homepage: <http://opencv.org>
* Docs: <http://docs.opencv.org/master/>
* Q&A forum: <http://answers.opencv.org>
* Issue tracking: <https://github.com/opencv/opencv/issues>

#### Contributing

Please read before starting work on a pull request: <https://github.com/opencv/opencv/wiki/How_to_contribute>

Summary of guidelines:

* One pull request per issue;
* Choose the right base branch;
* Include tests and documentation;
* Clean up "oops" commits before submitting;
* Follow the coding style guide.
1)安装依赖库：
$ sudo apt-get install gcc g++ cmake pkg-config build-essential
$ sudo apt-get install  libgtk2.0-dev libavcodec-dev libavformat-dev  libtiff5-dev  libswscale-dev libjasper-dev
2)解压opencv-3.1.0.zip到~/Opencv_Source
$ mkdir Opencv_Source
$ cd ./Opencv_Source
$ cp ~/Downloads/opencv-3.1.0.zip ./
$ unzip opencv-3.1.0.zip
$ cd opencv-3.1.0/
$ mkdir build
$ cd build
因为ippicv通常下载会失败，所以将刚刚下载的ippicv_linux_20151201.tgz复制到~/Opencv_Source/opencv-3.1.0/3rdparty/ippicv/downloads/Linux-808b791a6eac9ed78d32a7666804320e/文件夹下，没有的文件夹需要新建。放入后继续下面的命令
$ cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local .. 
$ make 
$ sudo make install 
（4）安装完成后，配置pkg-config，用于管理opencv安装库
$ sudo vim /etc/ld.so.conf
将下面的目录   /usr/local/lib    添加到文件中
$ sudo ldconfig -v
$ export  PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig 
使用以下命令查看pkg-config配置信息： pkg-config --libs opencv
（5）测试安装是否完成，测试程序采用opencv自带的sample：
$ cd ~/Opencv_Source/opencv-3.1.0/samples/
$ cmake .
$ make 
$ cd cpp/
里面就是刚刚make的文件，可以选择几个可执行文件进行执行，测试opencv是否安装成功

