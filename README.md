# MACpip-command-not-found-
解决MAC终端输入pip命令显示command not found的方法

出现这种问题的情况一般有两种，一种是电脑的Python版本落后（MAC自带python2版本 但是过于落后经常报错）；另一种是并没有安装pip 或者已安装的pip并不适配当下的python版本
可以在终端中输入
python --version
检查电脑默认的python版本 （现在比较新的是3.11）
如果终端输出显示的是当前版本是python 2 则需要先将python进行升级
首先前往python官网下载一个比较新的稳定版本（这部分安装一直点下一步即可）
安装成功后在终端中输入
which python3
终端会输出目前新版python的保存路径 把这段路径复制好
在终端中输入
open ~/.bash_profile
在最后一行写以下内容
alias python="/Library/Frameworks/Python.framework/Versions/3.9/bin/python3"
注意 自己操作的时候要把这句“”内的路径换成你刚才复制好的自己的路径
这时候电脑可能提示你这部分内容无权修改，只可以保存副本什么的 忽略就好
回车后其实就大功告成了
输入以下命令可以检查目前的python版本是不是已经更新好了
python --version
如果显示的版本更新成你刚才下载的了则说明python的版本现在没有问题了
此时如果pip的命令仍然显示无效 则更新一下pip即可
输入以下内容更新pip
python3 -m pip install --upgrade pip
输入后回车 就会看到下载的进度条 它会自动帮你下载并安装好合适的pip版本
这时候我们在终端里输入pip --version它可能还是显示没找到pip
这是因为这个命令不起效果 而不是pip没有安装成功
输入以下命令查看pip版本
python3 -m pip --version
回车后终端就会输出你刚才安装的pip版本和路径了
此时你可能粘贴别人的一段pip命令来安装东西什么的 它还是显示command not found
不用着急 这依旧不是你没有装好东西 只是单纯是这句唤醒它的命令无效而已
在你复制的pip命令前面加上python3 -m （注意m后面是有一个空格的）
就可以成功运行pip命令进行安装了
事实上 可能你在终端回复无效的命令行前面加上这个前缀的话 也许一开始就能解决问题
就像终端告诉我们的
“command not found”
"命令无效"
