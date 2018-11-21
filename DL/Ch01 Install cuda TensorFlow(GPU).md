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
    



