# Cheatsheet Linux General

## echo

output strings

**outputs "hello world" to console:**

```bash
echo "hello world"
```

```bash
hello world
```

## pwd

print working directory

```bash
pwd
```

```bash
/root
```

## cd

change folder

**change folder to /wfs/:**

```bash
cd /wfs/
```

## cp

copy files and folders

**create backup of setup.ini:**

```bash
cp setup.ini setup.ini.bck
```

## touch

create a file

**create file with name new.sh:**

```bash
touch new.sh
```

## tr

translates, deletes, and squeezes characters

**Print $PATH directories on a separate line**

```bash
echo $PATH | tr  ':' '\n'
```

```bash
/bin
/sbin
/usr/bin
/usr/sbin
```

**Remove the repeated space characters**

```bash
ps -ef | tr -s ' ' | grep terminal
```

```
user 23850 23849 0 10:30 ? 00:00:00 /usr/bin/xfce4-terminal -T Local Terminal -e check_passwd --disable-server --geometry 90x38
user 23915 23860 0 10:44 pts/0 00:00:00 grep --color=auto terminal

```

**Remove all non-numeric characters**

```bash
echo "IGEL Priority Plus phone number for US and Canada is 415-813-3933" | tr -cd [:digit:]
```

```bash
4158133933
```

## chmod

change file attributes

**make new.sh executable:**

```bash
chmod +x new.sh
```

## mkdir

create a folder

**create folder with name newdir:**

```bash
mkdir newdir
```

**create folder dir3 and make parent directories dir2 and dir1 if they do not exist**

```bash
mkdir -p /tmp/dir1/dir2/dir3
```

## rmdir

delete a folder

**delete folder with name newdir:**

```bash
rmdir newdir
```

## rm

delete a file

**delete file with name new.sh:**

```bash
rm new.sh
```

## ls

show directory content

**long list current directory:**

```bash
ls -l
```

```bash
total 96
drwxr-xr-x  3 root root     60 Mai 20 13:49 apparmor
drwxr-xr-x  2 root root     40 Mai 20 13:49 asset.events
-rw-r--r--  1 root root   2765 Mai 20 13:50 asset.ini
drwxr-xr-x  2 root root    100 Mai 20 13:50 ca-certs
drwxr-xr-x  2 root root     60 Mai 20 13:49 chrony
...
-rw-------  1 root root    106 Mai 20 13:50 systemkey
-rw-r--r--  1 root root     49 Mai 20 13:50 systemmd5
-rw-------  1 root root     32 Mai 20 13:49 tckey
-rw-------  1 root root    214 Mai 20 13:49 updateconf.ini
drwxr-xr-x 14 user users   440 Mai 20 13:50 user
drwxr-xr-x  2 root root     40 Mai 20 13:49 zoneinfo

```

## su

change to root

```bash
su
```

## vi

texteditor

**open setup.ini in vi:**

```bash
vi setup.ini
```

```bash
<system>
        <remotemanager>
                <server0>
                        ip=<igelrmserver.int.acme.org>
                </server0>
        </remotemanager>
        <icg>
                <server0>
                        host=<icg.acme.org>
                        uuid=<d8d43ff7a4274b8f96fb6ec96c4948>
....
        <drivers>
                currentdriver=<intel>
                currentconnectors=<lvds1,Seiko Epson Corporation,,1366,768,1366,768,0,0,,;>
        </drivers>
</x>
```

## kill

kill a running task by process id

**kill process with PID 48:**

```bash
kill 48
```

## killall

kill a running task by name

**kill process with name pnlogin:**

```bash
killall pnlogin 2>/dev/null
```

## ps

show running tasks

```bash
ps -aef
```

```bash
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 13:49 ?        00:00:03 /sbin/init 3
root         2     0  0 13:49 ?        00:00:00 [kthreadd]
root         3     2  0 13:49 ?        00:00:00 [rcu_gp]
root         4     2  0 13:49 ?        00:00:00 [rcu_par_gp]
root         6     2  0 13:49 ?        00:00:00 [kworker/0:0H-kb]
root         8     2  0 13:49 ?        00:00:00 [mm_percpu_wq]
root         9     2  0 13:49 ?        00:00:00 [ksoftirqd/0]
root        10     2  0 13:49 ?        00:00:00 [rcu_sched]
root        11     2  0 13:49 ?        00:00:00 [rcu_bh]
...
```

## cat

display the content of a file

**show contents of group.ini:**

```bash
cat group.ini
```

```bash
<services>
        <cisco_vxme_client>
                enabled=<true>
        </cisco_vxme_client>
        <ica_client>
                enabled=<true>
...
```

## less

less is more and allows backward movement (hit "b" key) in the file, as well as forward movement (hit "f" key), search for string (hit "/" key and enter string to search for), or to quit (hit "q" key)

**show contents of group.ini, hit key "f" to go forward, hit key "b" to go backward, hit key "/"  and the text to search for:**

```bash
less /wfs/group.ini
```

## more

display the content of a file page by page

**show contents of group.ini, hit space to continue to next page:**

```bash
more group.ini
```

```bash
<services>
        <cisco_vxme_client>
                enabled=<true>
        </cisco_vxme_client>
        <ica_client>
                enabled=<true>
...
```

## mount

mount a partition

**mount license folder writeable:**

```bash
mount -o remount,rw /license
```

## user_shutdown

shutdown the system

```bash
user_shutdown
```

## user_reboot

reboot the system

```bash
user_reboot
```

## grep

search for regular expression

**search for configured UMS server name:**

```bash
more /wfs/setup.ini | grep "ip="
```

```bash
                        ip=<igelrmserver.int.acme.org>
```

## top

task monitor

```bash
top
```

```bash
top - 14:15:59 up 26 min,  2 users,  load average: 0,05, 0,01, 0,01
Tasks: 236 total,   1 running, 168 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0,1 us,  0,1 sy,  0,0 ni, 99,8 id,  0,0 wa,  0,0 hi,  0,0 si,  0,0 st
KiB Mem :  1891000 total,   351040 free,   481452 used,  1058508 buff/cache
KiB Swap:  1134592 total,  1134592 free,        0 used.  1183616 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
18620 root      20   0   79776   4276   3520 R   0,3  0,2   0:00.02 top
    1 root      20   0  205624   9980   5812 S   0,0  0,5   0:03.88 systemd
    2 root      20   0       0      0      0 S   0,0  0,0   0:00.00 kthreadd
    3 root       0 -20       0      0      0 I   0,0  0,0   0:00.00 rcu_gp
    4 root       0 -20       0      0      0 I   0,0  0,0   0:00.00 rcu_par
...
```

## sleep

wait

**wait for 5 seconds:**

```bash
sleep 5
```

## watch

repeat periodic a command

**probe tcp port 8443 on igelrmserver every 2 seconds:**

```bash
watch probeport igelrmserver 8443
```

```bash
Every 2,0s: probeport igelrmserver 8443                                                                                                                       ITCA44CC8C90000: Wed May 20 14:24:08 2020

Connection successful
```

## which

locate command

**locate command nmcli:**

```bash
which nmcli
```

```bash
/usr/bin/nmcli
```

## uname

show linux details

```bash
uname
```

```bash
Linux
```

## date

date tool

**show date:**

```bash
date
```

```bash
Mi 19. Mai 19:26:59 CEST 2020
```

## systemctl

service handler

**restart network:**

```bash
systemctl restart network-manager
```

## comm

compare two sorted files line by line

**Simple method to determine command line to run (such as IGEL setup or IGEL About):**

```bash
# what processes are running BEFORE item is run?
ps -ef | sort > /tmp/ps1.txt

# what processes are running AFTER item is run?
ps -ef | sort > /tmp/ps2.txt

# what are the new processes?
# comm only showing processes in /tmp/ps2.txt
comm -1 -3 /tmp/ps1.txt /tmp/ps2.txt
```

**Start IGEL setup:** `/bin/bash /config/bin/start_setup`

**Start IGLE About:** `applauncher -style gtk2 --aboutOnly`

## compgen

list all the linux commands (including bash shell aliases and functions)

**list all igel and remotemanager related commands**:

```bash
compgen -c | egrep "igel|_rm" | sort | more
```

```bash
get_rmdirlist
get_rmsettings
get_rmsettings_boot
...
igel_showsplash
igel-shutdown-debug
igel-shutdown-inhibitor
--More--
```

## xinput

utility to configure and test X input devices

**list all input devices:**

```bash
xinput --list
```
```bash
⎡ Virtual core pointer                    	id=2	[master pointer  (3)]
⎜   ↳ Virtual core XTEST pointer              	id=4	[slave  pointer  (2)]
⎜   ↳ 3830303142534F54:00 06CB:CE46 Mouse     	id=11	[slave  pointer  (2)]
⎜   ↳ Logitech USB-PS/2 Optical Mouse         	id=9	[slave  pointer  (2)]
⎜   ↳ 3830303142534F54:00 06CB:CE46 Touchpad  	id=12	[slave  pointer  (2)]
⎣ Virtual core keyboard                   	id=3	[master keyboard (2)]
    ↳ Virtual core XTEST keyboard             	id=5	[slave  keyboard (3)]
    ↳ Toshiba input device                    	id=14	[slave  keyboard (3)]
    ↳ Video Bus                               	id=6	[slave  keyboard (3)]
    ↳ Power Button                            	id=7	[slave  keyboard (3)]
    ↳ Sleep Button                            	id=8	[slave  keyboard (3)]
    ↳ AT Translated Set 2 keyboard            	id=13	[slave  keyboard (3)]
    ↳ Web Camera - HD: Web Camera - H         	id=10	[slave  keyboard (3)]
```

**disable touchpad:**

```bash
xinput set-prop "3830303142534F54:00 06CB:CE46 Touchpad" "Device Enabled" 0
```

## xset

user preference utility for X

[Screen Blanking](https://shallowsky.com/linux/x-screen-blanking.html)

**testing dpms signal for monitor to turn off, waiting 15 seconds, then signal monitor to turn on**

```bash
sleep 1; xset dpms force off; sleep 15; xset dpms force on;
```
**commands to trigger the various states**

```bash
sleep 1; xset s activate;  # will blank the screen (or activate the screensaver program, if you're using one) after a delay of one second
sleep 1; xset dpms force off;  # dpms turn the screen OFF after a delay of one second.
sleep 1; xset dpms force standby;  # dpms screen standby after a delay of one second.
sleep 1; xset dpms force suspend;  # dpms screen suspend after a delay of one second.
sleep 1; xset dpms force on;  # dpms screen ON after a delay of one second.
```

## wmctrl

List windows managed by the window manager

```bash
wmctrl -l  
  ```  

Close VMware window

```bash
wmctrl -c VMware
  ```
