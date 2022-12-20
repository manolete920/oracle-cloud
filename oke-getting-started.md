# Provision Oracle Cloud Developer



## login

```bash
manolete919@SIS_CEN1_071:~$ cd oracle/
manolete919@SIS_CEN1_071:~/oracle$ ssh -i private.key opc@129.213.127.9
```



## update

```bash
sudo yum -y update --skip-broken
```



## install vnc viewer

```bash
tightvnc-2.8.63-gpl-setup-64bit.msi
```

## Activating server

```bash
manolete919@SIS_CEN1_071:~/oracle$ ssh -i private.key opc@129.153.47.242
The authenticity of host '129.153.47.242 (129.153.47.242)' can't be established.
ECDSA key fingerprint is SHA256:jaHI7saiRnnkEGKqQCMYigYYa000FIfXgzWwS4zAskU.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '129.153.47.242' (ECDSA) to the list of known hosts.
Activate the web console with: systemctl enable --now cockpit.socket

[opc@mgr-vm-dev01 ~]$ vncserver

WARNING: vncserver has been replaced by a systemd unit and is about to be removed in future releases.
Please read /usr/share/doc/tigervnc/HOWTO.md for more information.

You will require a password to access your desktops.

Password:
Verify:
Would you like to enter a view-only password (y/n)? n
A view-only password is not used
xauth:  file /home/opc/.Xauthority does not exist

New 'mgr-vm-dev01:1 (opc)' desktop is mgr-vm-dev01:1

Creating default startup script /home/opc/.vnc/xstartup
Creating default config /home/opc/.vnc/config
Starting applications specified in /home/opc/.vnc/xstartup
Log file is /home/opc/.vnc/mgr-vm-dev01:1.log
```

doc

```
https://www.linuxtopia.org/HowToGuides/VNC_setup_Linux_Windows.html
```

## kill

```bash
[opc@mgr-vm-dev01 ~]$ vncserver -kill :1

WARNING: vncserver has been replaced by a systemd unit and is about to be removed in future releases.
Please read /usr/share/doc/tigervnc/HOWTO.md for more information.
Killing Xvnc process ID 8724
```

## create a tunnel

```bash
ssh -i private.key -L 5901:localhost:5901 opc@129.153.47.242
```

## TightVNC

```bash
localhost:5901
```

