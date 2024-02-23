## YOLO的安装

### Python版本为3.11.8

```bash
$ unzip Python-3.11.8.zip
$ cd Python-3.11.8.zip
$ sudo make install
```



### ultralytics

> pip install ultralytics

##### 所需依赖

- numpy

  > pip install numpy-1.26.4-cp311-cp311-linux_riscv64.whl

- pillow

  > 先尝试进行正常的安装
  >
  > pip install pillow-10.2.0-cp311-cp311-linux_riscv64.whl
  >
  > 如果出现需要`jpeg`库等情况，运行以下命令
  >
  > ```bash
  > $ sudo apt update
  > $ sudo apt-get install libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev \
  >     libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python3-tk \
  >     libharfbuzz-dev libfribidi-dev libxcb1-dev
  > ```
  >
  > 

- matplotlib

  > pip install matplotlib-3.8.3-cp311-cp311-linux_riscv64.whl

- opencv-python

  > pip install opencv_python-4.9.0.80-cp311-cp311-linux_riscv64.whl

- scipy

  > 先尝试正常的安装
  >
  > pip install scipy-1.12.0-cp311-cp311-linux_riscv64.whl
  >
  > 如果需要`OpenBLAS`，运行以下命令
  >
  > ```bash
  > $ unzip OpenBLAS-0.3.26.zip
  > $ cd OpenBLAS-0.3.26
  > $ sudo make install
  > ```
  >
  > 

- torch

  > pip install torch-2.1.0a0+gitunknown-cp311-cp311-linux_riscv64.whl

- torchvision

  > pip install torchvision-0.16.2-cp311-cp311-linux_riscv64.whl

- pandas

  > pip install pandas-2.2.0-cp311-cp311-linux_riscv64.whl

- 剩余的依赖还有`pyyaml`、`requests`、`tqdm`、`psutil`、`py-cpuinfo`、`thop`、`seaborn`，可以在安装`ultralytics`时交由`pip`进行安装。
- 以下为`ultralytics`的依赖图

![ultralytics依赖图](.\img\ultralytics.png)

##### 导入问题

在`Python`中进行导入时，如果出现`_bz2`或`_lzma`包不存在的问题，请在确保`pillow`安装时要求用`apt`安装的软件包已安装的情况下，尝试以下命令

```bash
# 请在这里输入/usr/lib/中存在的python文件夹，这里以python3.11举例
$ ver=python3.11

# _bz2.cpython-311-riscv64-linux-gnu.so包的拷贝方式
$ sudo cp /usr/lib/$ver/lib-dynload/_bz2.cpython-311-riscv64-linux-gnu.so /usr/local/lib/python3.11/lib-dynload

# _lzma.cpython-311-riscv64-linux-gnu.so包的拷贝方式
$ sudo cp /usr/lib/$ver/lib-dynload/_lzma.cpython-311-riscv64-linux-gnu.so /usr/local/lib/python3.11/lib-dynload
```

