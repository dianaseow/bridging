# LAB LInux service
diana@BATCOM:~$ pwd
/home/diana
diana@BATCOM:~$ ls
README.md  dianaseow  linux-lab
diana@BATCOM:~$ ls -l
total 12
-rw-r--r-- 1 diana diana   12 Jan 17 16:05 README.md
drwxr-xr-x 3 diana diana 4096 Jan 17 19:36 dianaseow
drwxr-xr-x 5 diana diana 4096 Jan 11 15:58 linux-lab
diana@BATCOM:~$ ls
README.md  dianaseow  linux-lab
diana@BATCOM:~$ cd /
pwd
/
diana@BATCOM:/$ cd home
ls
cd your_username
diana
-bash: cd: your_username: No such file or directory
diana@BATCOM:/home$ mkdir lab_test
ls
mkdir: cannot create directory ‘lab_test’: Permission denied
diana
diana@BATCOM:/home$ touch lab1.txt
ls
touch: cannot touch 'lab1.txt': Permission denied
diana
diana@BATCOM:/home$ ls /
bin                home               lost+found  root                srv
bin.usr-is-merged  init               media       run                 sys
boot               lib                mnt         sbin                tmp
dev                lib.usr-is-merged  opt         sbin.usr-is-merged  usr
etc                lib64              proc        snap                var
diana@BATCOM:/home$ man ls
diana@BATCOM:/home$ diana@BATCOM:~$ pwd
/home/diana
diana@BATCOM:~$ ls
README.md  dianaseow  linux-lab
diana@BATCOM:~$ ls -l
total 12
-rw-r--r-- 1 diana diana   12 Jan 17 16:05 README.md
drwxr-xr-x 3 diana diana 4096 Jan 17 19:36 dianaseow
drwxr-xr-x 5 diana diana 4096 Jan 11 15:58 linux-lab
diana@BATCOM:~$ ls
README.md  dianaseow  linux-lab
diana@BATCOM:~$ cd /
pwd
/
diana@BATCOM:/$ cd home
ls
cd your_username
diana
-bash: cd: your_username: No such file or directory
diana@BATCOM:/home$ mkdir lab_test
ls
mkdir: cannot create directory ‘lab_test’: Permission denied
diana
diana@BATCOM:/home$ touch lab1.txt
ls
touch: cannot touch 'lab1.txt': Permission denied
diana
diana@BATCOM:/home$ ls /
bin                home               lost+found  root                srv
bin.usr-is-merged  init               media       run                 sys
boot               lib                mnt         sbin                tmp
dev                lib.usr-is-merged  opt         sbin.usr-is-merged  usr
etc                lib64              proc        snap                var
diana@BATCOM:/home$ man ls
diana@BATCOM:/home$ man ls
diana@BATCOM:/home$ systemctl list-units --type=service
  UNIT                                     LOAD   ACTIVE     SUB          D>
  apache2.service                          loaded active     running      T>
  console-getty.service                    loaded active     running      C>
  console-setup.service                    loaded active     exited       S>
  cron.service                             loaded active     running      R>
  dbus.service                             loaded active     running      D>
  getty@tty1.service                       loaded active     running      G>
  keyboard-setup.service                   loaded active     exited       S>
  kmod-static-nodes.service                loaded active     exited       C>
  rsyslog.service                          loaded active     running      S>
  setvtrgb.service                         loaded active     exited       S>
  snapd.seeded.service                     loaded active     exited       W>
  ssh.service                              loaded active     running      O>
  systemd-binfmt.service                   loaded active     exited       S>
  systemd-journal-flush.service            loaded active     exited       F>
  systemd-journald.service                 loaded active     running      J>
  systemd-logind.service                   loaded active     running      U>
  systemd-modules-load.service             loaded active     exited       L>
  systemd-remount-fs.service               loaded active     exited       R>
  systemd-resolved.service                 loaded active     running      N>
  systemd-sysctl.service                   loaded active     exited       A>
  systemd-timesyncd.service                loaded active     running      N>
  systemd-tmpfiles-setup-dev-early.service loaded active     exited       C>
  systemd-tmpfiles-setup-dev.service       loaded active     exited       C>
  systemd-tmpfiles-setup.service           loaded active     exited       C>
  systemd-udev-trigger.service             loaded active     exited       C>
  systemd-udevd.service                    loaded active     running      R>
  systemd-update-utmp.service              loaded active     exited       R>
  systemd-user-sessions.service            loaded active     exited       P>
diana@BATCOM:/home$ sudo systemctl status ssh
[sudo] password for diana:
Sorry, try again.
[sudo] password for diana:
Sorry, try again.
[sudo] password for diana:
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; enabled; preset: >
     Active: active (running) since Sat 2026-01-17 16:04:01 +08; 4h 7min ago
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 204 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCC>
   Main PID: 233 (sshd)
      Tasks: 1 (limit: 9335)
     Memory: 1.9M (peak: 2.5M)
        CPU: 38ms
     CGroup: /system.slice/ssh.service
             └─233 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

Jan 17 16:04:01 BATCOM systemd[1]: Starting ssh.service - OpenBSD Secure Sh>
Jan 17 16:04:01 BATCOM sshd[233]: Server listening on 0.0.0.0 port 22.
Jan 17 16:04:01 BATCOM sshd[233]: Server listening on :: port 22.
Jan 17 16:04:01 BATCOM systemd[1]: Started ssh.service - OpenBSD Secure She>
diana@BATCOM:/home$ sudo systemctl stop cron
sudo systemctl status cron
○ cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset:>
     Active: inactive (dead) since Sat 2026-01-17 20:12:11 +08; 22ms ago
   Duration: 4h 8min 10.208s
       Docs: man:cron(8)
    Process: 172 ExecStart=/usr/sbin/cron -f -P $EXTRA_OPTS (code=killed, s>
   Main PID: 172 (code=killed, signal=TERM)
        CPU: 48ms

Jan 17 16:04:01 BATCOM systemd[1]: Started cron.service - Regular backgroun>
Jan 17 16:04:01 BATCOM (cron)[172]: cron.service: Referenced but unset envi>
Jan 17 16:04:01 BATCOM cron[172]: (CRON) INFO (pidfile fd = 3)
Jan 17 16:04:01 BATCOM cron[172]: (CRON) INFO (Running @reboot jobs)
Jan 17 16:17:01 BATCOM CRON[755]: pam_unix(cron:session): session opened fo>
Jan 17 16:17:01 BATCOM CRON[756]: (root) CMD (cd / && run-parts --report /e>
Jan 17 16:17:01 BATCOM CRON[755]: pam_unix(cron:session): session closed fo>
Jan 17 20:12:11 BATCOM systemd[1]: Stopping cron.service - Regular backgrou>
Jan 17 20:12:11 BATCOM systemd[1]: cron.service: Deactivated successfully.
Jan 17 20:12:11 BATCOM systemd[1]: Stopped cron.service - Regular backgroun>
diana@BATCOM:/home$ cd ~
touch testfile.txt
ls -l testfile.txt
-rw-r--r-- 1 diana diana 0 Jan 17 20:12 testfile.txt
diana@BATCOM:~$ chmod 755 testfile.txt
ls -l testfile.txt
-rwxr-xr-x 1 diana diana 0 Jan 17 20:12 testfile.txt
diana@BATCOM:~$ sudo chown $USER:$USER testfile.txt
ls -l testfile.txt
-rwxr-xr-x 1 diana diana 0 Jan 17 20:12 testfile.txt
diana@BATCOM:~$ echo "Linux is powerful" > testfile.txt
diana@BATCOM:~$ grep -r "Linux" ~
/home/diana/testfile.txt:Linux is powerful
/home/diana/.bash_history:Searching and Navigating the Linux File System 

