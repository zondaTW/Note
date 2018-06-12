# SSH

## Install  
`sudo pacman -S openssh`  

## Configuration
`sudo vim /etc/ssh/sshd_config`  
加上`PermitRootLogin yes` (讓root能登入)  
加上`Port 2222` (更改Port，預設Port 22)  
將`ListenAddress 0.0.0.0`的`#`拿掉  

## Start
`sudo systemctl start sshd`  

## Boot
`sudo systemctl enable sshd`  