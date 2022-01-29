# Bandit
## 通关过程
## Level0 
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.
Win:使用ssh连接工具 xshell, putty, securecrt等连接远端服务器
Mac: 终端
Linux: Terminal 终端
```bash
SSH Information
Host: bandit.labs.overthewire.org
Port: 2220 
```
username:bandit0, password: bandit0.
```bash
ssh bandit0@bandit.labs.overthewire.org -P 22220
输入密码bandit0
```

```
Host 'bandit.labs.overthewire.org' resolved to 176.9.9.172.
Connecting to 176.9.9.172:2220...
Connection established.
To escape to local shell, press 'Ctrl+Alt+]'.

This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

Linux bandit.otw.local 5.4.8 x86_64 GNU/Linux

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to Steven or morla on
irc.overthewire.org.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ and /proc/ is disabled
  so that users can not snoop on eachother. Files and directories with
  easily guessable or short names will be periodically deleted!

  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few usefull tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /usr/local/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /usr/local/pwndbg/
    * peda (https://github.com/longld/peda.git) in /usr/local/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /usr/local/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)
    * checksec.sh (http://www.trapkit.de/tools/checksec.html) in /usr/local/bin/checksec.sh

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us through IRC on
  irc.overthewire.org #wargames.

  Enjoy your stay!

```

## Level 0 → Level 1
Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
```bash
bandit0@bandit:~$ pwd
/home/bandit0
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
bandit0@bandit:~$ 
```
登录Level1的终端机器
```bash
ssh bandit1@bandit.labs.overthewire.org -P 2220
输入密码: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```
```
bandit1@bandit:~$ 
bandit1@bandit:~$ ls -ltr
total 4
-rw-r----- 1 bandit2 bandit1 33 May  7  2020 -
bandit1@bandit:~$ df -h
Filesystem            Size  Used Avail Use% Mounted on
udev                  2.0G     0  2.0G   0% /dev
tmpfs                 394M  6.6M  387M   2% /run
/dev/mapper/vg0-root   19G  3.0G   15G  17% /
tmpfs                 5.0M  1.6M  3.5M  32% /run/lock
tmpfs                 787M     0  787M   0% /run/shm
/dev/mapper/vg0-boot  4.7G   71M  4.4G   2% /boot
/dev/mapper/vg0-tmp    15G  523M   13G   4% /tmp
bandit1@bandit:~$ du -ms 
1	.
bandit1@bandit:~$ 
bandit1@bandit:~$ 
bandit1@bandit:~$ 
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ ls -tlr
total 4
-rw-r----- 1 bandit2 bandit1 33 May  7  2020 -
bandit1@bandit:~$ cat `pwd`/-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
或
bandit1@bandit:~$ cat /home/bandit1/-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

```
## Level 1 → Level 2
The password for the next level is stored in a file called - located in the home directory

```
ssh bandit2@bandit.labs.overthewire.org -P 2220
输入密码: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ ls -tlr
total 4
-rw-r----- 1 bandit3 bandit2 33 May  7  2020 spaces in this filename
bandit2@bandit:~$ 
bandit2@bandit:~$ 
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
