Anaconda + Cuda9.0（暂时tensorflow最高支持） + tensorflow（GPU版本）的安装记录
======
第一步：安装Anaconda
----
cat /etc/issue 查看系统版本号<br>
Ubuntu 16.04.5 LTS \n \l<br>
<br>
上官网https://www.anaconda.com/download/#linux <br>
<br>
知道下载地址https://repo.anaconda.com/archive/Anaconda3-5.3.1-Linux-x86_64.sh<br>
<br>
<br>
<br>
在~/ 目录下<br>
<br>
<br>
    mkdir Anaconda<br>
    cd Anaconda<br>
    wget https://repo.anaconda.com/archive/Anaconda3-5.3.1-Linux-x86_64.sh<br>
    bash Anaconda3-5.3.1-Linux-x86_64.sh<br>
然后就yes，默认目录就刷刷地装好Anaconda<br>
<br>
source ~/.bashrc 激活个人用户的环境变量<br>
其实就是激活了下图的变量<br>
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/001.PNG)
<br>
<br>
当打入python命令后有弹出Anaconda的字就完成了
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/002.PNG)
<br>
<br>
<br>
<br>
第二步：使用conda的Python虚拟环境（virtualenv）
----
<br>
使用 conda create -n your_env_name python=X.X（2.7、3.6等)<br>
命令创建python版本为X.X、名字为your_env_name的虚拟环境。<br>
your_env_name文件可以在Anaconda安装目录envs文件下找到。<br>

conda create -n tensorflow python=3.6<br>
<br>
<br>
<br>
source activate tensorflow 激活虚拟环境<br>
deactivate                 退出虚拟环境<br>
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/003.PNG)<br>
<br>
<br>
conda install -n your_env_name [package]即可安装package到your_env_name中<br>
<br>
<br>
<br>
第三步：安装cuda（英伟达的计算平台）
----
cuda下载地址 https://developer.nvidia.com/cuda-92-download-archive？target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=runfilelocal<br>
<br>
<br>
<br>
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/004.PNG)<br>
<br>
<br>
$ chmod +x cuda_9.2.148_396.37_linux.run<br>
$ ./cuda_9.2.148_396.37_linux.run --extract=$HOME<br>
<br>
<br>
解压出来有三个文件分别是NVIDIA-Linux-x86_64-396.37.run（显卡驱动不装），cuda-linux.9.2.148-24330188.run（需要安装），cuda-samples.9.2.148-24330188-linux.run（需要安装）<br>
<br>
<br>
安装<br>
sudo ./cuda-linux.9.2.148-24330188.run<br>
sudo ./cuda-samples.9.2.148-24330188-linux.run<br>
<br>
<br>
变量设定<br>
$ sudo bash -c "echo /usr/local/cuda/lib64/ > /etc/ld.so.conf.d/cuda.conf"<br>
$ sudo ldconfig<br>
<br>
<br>
添加环境变量<br>
sudo vim /etc/environment and add :/usr/local/cuda/bin<br>
<br>
<br>
编译样例，过程会有点长<br>
$ cd /usr/local/cuda-9.0/samples<br>
$ sudo make<br>
<br>
<br>
<br>
对样例进行测试<br>
$ cd /usr/local/cuda/samples/bin/x86_64/linux/release<br>
$ ./deviceQuery<br>
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/005.PNG)<br>
<br>
<br>

第四步：安装cuDNN 7.4.1
----
上官网https://developer.nvidia.com/rdp/cudnn-download下载以下三个文件<br>
![](https://github.com/thejhacker/Artificial-Intelligence/raw/master/Image/006.PNG)<br>
<br>
<br>
$ sudo dpkg -i libcudnn7_7.4.1.5-1+cuda9.2_amd64.deb (the runtime library)<br>
<br>
$ sudo dpkg -i libcudnn7-dev_7.4.1.5-1+cuda9.2_amd64.deb (the developer library)<br>
<br>
$ sudo dpkg -i libcudnn7-doc_7.4.1.5-1+cuda9.2_amd64.deb (the code samples)<br>
<br>
<br>
测试<br>
<br>
cd /usr/src/cudnn_samples_v7/mnistCUDNN<br>
make clean && make<br>
./mnistCUDNN<br>
<br>
出现pass字样就完成了<br>
<br>
<br>
还需要设置环境变量<br>
在~/.bashrc后面加上下面这句话<br>
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/extras/CUPTI/lib64"<br>
source ~/.bashrc<br>
<br>
<br>
第五步：安装tensorflow
----
要确定python版本为3.5<br>
pip3 install --upgrade tensorflow-gpu<br>
<br>




