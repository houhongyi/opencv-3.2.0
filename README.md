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



### 这是一个opencv3.2.0并附带有opencv_contrib的源码库，同时还包含了编译与安装所需的相应下载依赖软件。
安装可遵循一下命令：

#### 安装依赖


* sudo apt-get install build-essential
* sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
* sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
#### 在opencv的目录下创建build文件夹并进入

* cd opencv-3.2.0/build

#### Cmake

* cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=/home/happy/opencv-3.2.0/opencv_contrib/modules/ ..

#### make和install

* make -j8
* sudo make install

### 在clion中调用给出一个CMakeList.txt示例
cmake_minimum_required(VERSION 3.6)

project(OpencvTest)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CUDA_USE_STATIC_CUDA_RUNTIME OFF) #禁用CUDA

set(SOURCE_FILES main.cpp)


find_package(OpenCV REQUIRED) #查找opencv包

add_executable(OpencvTest ${SOURCE_FILES})

target_link_libraries(OpencvTest ${OpenCV_LIBS}) #加入opencv lib
