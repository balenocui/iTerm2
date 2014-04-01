iTerm2
======

This script can be used to automate ZModem transfers from your OSX desktop to a server that can run lrzsz (in theory, any machine that supports SSH), and vice-versa.

The minimum supported iTerm2 version is 1.0.0.20120108

Setup is pretty simple:

Save the iterm2-send-zmodem.sh and iterm2-recv-zmodem.sh scripts in /usr/local/bin/
Set up Triggers in iTerm 2 like so:
<pre>
    Regular expression: \*\*B0100
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-send-zmodem.sh
    
    
    Regular expression: \*\*B00000000000000
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
</pre>    
    
To send a file to a remote machine:

1. Type "rz" on the remote machine
2. Select the file(s) on the local machine to send
3. Wait for the coprocess indicator to disappear

The receive a file from a remote machine

1. Type "sz filename1 filename2 …filenameN" on the remote machine
2. Select the folder to receive to on the local machine
3. Wait for the coprocess indicator to disappear



中文说明：
=========
保存脚本文件 iterm2-send-zmodem.sh 和 iterm2-recv-zmodem.sh 到/usr/local/bin(保证有可执行权限chmod +x)
修改iTerm2的default trigger（iTerm偏好设置-> Profiles –> Default –> Advanced –> Triggers的Edit按钮）
在规则中加入两项：
<pre>
    Regular expression: \*\*B0100
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-send-zmodem.sh
    
    
    Regular expression: \*\*B00000000000000
    Action: Run Silent Coprocess
    Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
</pre>    

发送文件到远端服务器

1. 在远端服务器执行rz
2. 本地选择文件传输
3. 等待传输指示消失

接收远端服务器的文件

1. 再远端服务器执行sz filename1 filename2 … filenameN
2. 本地选择目录保存
3. 等待传输指示消失
