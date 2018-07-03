# screen 
## 使用Screen
1. 创建screen窗口
	- screen
	- screen vi test.c
	- 我们还可以在一个已有screen会话中创建新的窗口。在当前screen窗口中键入C-a c，即Ctrl键+a键，之后再按下c键，screen 在该会话内生成一个新的窗口并切换到该窗口
## 会话恢复
1. 重新连接会话
	- 可以不中断screen窗口中程序的运行而暂时断开（detach）screen会话，并在随后时间重新连接（attach）该会话，重新控制各窗口中运行的程序。例如，我们打开一个screen窗口编辑/tmp/abc文件： screen vi /tmp/abc
	- 之后我们想暂时退出做点别的事情，比如出去散散步，那么在screen窗口键入C-a d，Screen会给出detached提示：暂时中断会话
	- 半个小时之后回来了，找到该screen会话：
		* screen -ls
		* screen -r <screen_pid>重新连接上
		* screen -list，显示会话状态
		* screen -wipe清除该会话

## 保存
1. 保存screen
	- 只需要打开一个ssh窗口，创建需要的screen窗口，退出的时候C-a d“保存”你的工作，下次登录后直接screen -r <screen_pid>就可以了
	- 最好能给每个窗口起一个名字，这样好记些。使用C-a A给窗口起名字。使用C-a w可以看到这些窗口名字，可能名字出现的位置不同