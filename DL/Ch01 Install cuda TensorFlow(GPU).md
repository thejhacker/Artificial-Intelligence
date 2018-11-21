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
第二步：安装Python虚拟环境（virtualenv）
----


