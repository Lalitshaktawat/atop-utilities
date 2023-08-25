:bell: **atop command utilities**

:gift: I am already having Ubuntu flavor machine ready in my hand. So I am going to try it with this OS. Yes, we can do the same with all OS. Only the installation command would be different.

```R
# The atop command is a tool for monitoring system resources in Linux. It displays tons of information related to the amount of load on the system’s resources at the process level.
```

:hourglass: **Installation**
```R
# apt install atop
# atop
```

<img alt="gcp" src="/pic/atop.png" class="lazy" width="100%"> 

:bulb: **Cumulative Statistics of the atop command**

:o: PRC - stands for **process**.

```R
# The first two values are the time consumed by the 'sys' (system) and 'user' processes.
# It is followed by the total number of processes as '#proc'.
# The next value is the number of threads currently running in the system. ('#trun')
# '#tslpi' denotes the number of threads that are currently sleeping and interruptible.
# '#tslpu' denotes the number of threads that are currently sleeping and uninterruptible.
# The following value is the number of zombie processes.
# Next up is the number of clone system calls.
# The last value is the number of processes that ended during the elapsed time. ('#exit')
```
:o: **Performance-related Statistics**

```R
CPU - relates to CPU utilization.
# The first two values show the percentage utilization of all the cores by the system and user processes.
# The percentage of CPU used for interrupt requests. ('irq')
# The next value is the idle percentage for all the cores combined.
# The following value denotes the waiting each CPU core had to do.
# Next up is the percentage for the steal time.
# 'guest' denotes the guest-percentage, which is the CPU time spent on other virtual machines.
# The last two values indicate the current frequency of the CPU.
```

:o: **Now, the 'atop' displays the above statistics for each core independently.**
```R
CPL - refers to as CPU Load.
# The first three values are the average loads with different periods: 1, 5, and 15 minutes.
# This is followed by the number of context switches ('csw')
# Next up is the number of interrupts ('intr')
# The last value is number of available CPUs.
```

<img alt="gcp" src="/pic/mem.png" class="lazy" width="100%"> 

:bulb: **Memory-related Statistics**
```R
MEM - Memory Utilization
# The total physical memory supported.
# The memory currently free.
# The current cache memory.
# 'buff' as in “buffer” is the amount of memory consumed in filesystem meta-data.
# The sum of memory for kernel’s memory allocation shown as 'slab'.
# The amount of shared memory.
# SWP - Swap Memory.
```

:bulb: **Disk-related Statistics**

<img alt="gcp" src="/pic/disk.png" class="lazy" width="100%"> 

```R
# DSK - Disk usage
# The first value denotes the percentage of time the system is busy handling requests.
# The reading requests issued.
# The writing requests issued.
# The rate at which data (in KB) is read per reading request.
# The rate at which data (in KB) is written per writing request.
# The next two values are time rates for reading and writing on the disk in Megabytes.
# The last value is the average number of milliseconds spent in handling requests.
```

:bulb: **Network-related Statistics**
```R
# NET - Network Statistics at the Transport Layer
# 'transport' signifies the Transport layer in Networking, which deals with the data protocols.
# The number of segments received by the system following the TCP protocol. ('tcpi')
# The number of segments transmitted. ('tcpo')
# The similar statistics for UCP protocol. ('udpi' for UDP in) and ('udpo' for UDP out).
# 'tcpao' is the number of active TCP open connections.
# Opposite to previous 'tcppo' is the number of passive TCP connections, but still open.
# The figure of TCP retransmissions as 'tcprs'.
# The figure of UDP input errors as 'udpie'.
# NET - Network Statistics at the Network Layer
# 'network' signifies the Network Layer, which deals with Internet Protocols, IPv4 and IPv6 combined.
# The number of IP packets received by the network interfaces. ('ipi')
# The number of IP packets transmitted out from the interfaces. ('ipo')
# The quantity of IP packets forwarded to other interfaces. ('ipfrw')
# The quantity of IP packets delivered. ('deliv')
# The last two entries are the number of ICMP packets received and transmitted by the network interfaces.

The following lines refer to each active network interface.

# The first value is the name of the network interface, like 'wlp19s0'.
# The following two packets are the number of packets that were received and transmitted through the particular interface. ('pcki' and 'pcko')
# The network speed in Megabits (Mbps) as 'sp'.
# The rate at which bits are received and transmitted per second. ('si' and 'so')
# The number of errors in packets received and transmitted. ('erri' and 'erro').
# The last two values are the dropped packets in both ways. ('drpi' and 'drpo')
```

:dizzy: **System Resources for each process.**
| **PID**    	| **The process ID**                                                                      	|
|------------	|-----------------------------------------------------------------------------------------	|
| **SYSCPU** 	| The amount of CPU consumed by the process while system handling.                        	|
| **USRCPU** 	| The amount of CPU consumed by the process , during its running in user mode.            	|
| **VGROW**  	| The amount of virtual memory that the process has occupied since the last value update. 	|
| **RGROW**  	| The amount of resident (physical) memory grown since last value update.                 	|
| **RDDSK**  	| The size of data transferred during disk reads.                                         	|
| **WRDSK**  	| The size of data transferred during disk writes.                                        	|
| **RUID**   	| The real user ID under which the process is being executed.                             	|
| **EUID**   	| The effective user ID under which the process is being executed.                        	|
| **ST**     	| The current status of the process.                                                      	|
| **EXC**    	| The exit code after the process terminates.                                             	|
| **THR**    	| The number of threads within the process.                                               	|
| **S**      	| The current status of the primary thread of the process.                                	|
| **CPU**    	| The percentage of CPU utilization of the entire process.                                	|
| **CMD**    	| The name of the process.                                                                	|


:dizzy: **The memory-based output of the atop command.**

```R
# atop -m
```

| **ID**    	| Detail.                                                                                	|
|------------	|------------------------------------------------------------------------------------------------	|
| **PID**    	| The process 
| **TID**    	| The thread ID.                                                                                 	|
| **MINFLT** 	| The number of minor page faults that have been solved by accessing data from free pages.       	|
| **MAJFLT** 	| The number of major page faults that have been solved by especially retrieving data from disk. 	|
| **VSTEXT** 	| The virtual memory occupied by the process text.                                               	|
| **VSLIBS** 	| The virtual memory occupied by the shared libraries of the process.                            	|
| **VDATA**  	| The virtual memory size of the private data of the process.                                    	|
| **VSTACK** 	| The virtual memory size of the private stack of the process.                                   	|
| **VSIZE**  	| The total virtual memory size of the process.                                                  	|
| **RSIZE**  	| The total resident memory occupied by the process.                                             	|
| **MEM**    	| The percentage of RAM consumed by the process.                                                 	|

:dizzy: **Disk-specific output using the atom command in Linux.**

```R
# atop -d
```

| **ID**  	| Details          	|
|------------	|----------------------------------------------------------	|
| **RDDSK**  	| The size of data transferred during disk reads.          	|
| **WRDSK**  	| The size of data transferred during disk writes.         	|
| **WCANCL** 	| The size of data initially written, but later withdrawn. 	|
| **DSK**    	| The percentage of Disk occupied.                         	|
| **CMD**    	| The name of the process.                                 	|

:pencil: Yes, More option are in the list.

```R
# atop -h
Usage: atop [-flags] [interval [samples]]
                or
Usage: atop -w  file  [-S] [-a] [interval [samples]]
       atop -r [file] [-b [YYYYMMDD]hhmm] [-e [YYYYMMDD]hhmm] [-flags]

        generic flags:
          -V  show version information
          -a  show or log all processes (i.s.o. active processes only)
          -R  calculate proportional set size (PSS) per process
          -W  determine WCHAN (string) per thread
          -P  generate parseable output for specified label(s)
          -Z  no spaces in parseable output for command (line)
          -L  alternate line length (default 80) in case of non-screen output
          -f  show fixed number of lines with system statistics
          -F  suppress sorting of system resources
          -G  suppress exited processes in output
          -l  show limited number of lines for certain resources
          -y  show threads within process
          -Y  sort threads (when combined with 'y')
          -1  show average-per-second i.s.o. total values

          -x  no colors in case of high occupation
          -g  show general process-info (default)
          -m  show memory-related process-info
          -d  show disk-related process-info
          -n  show network-related process-info
          -s  show scheduling-related process-info
          -v  show various process-info (ppid, user/group, date/time)
          -c  show command line per process
          -o  show own defined process-info
          -u  show cumulated process-info per user
          -p  show cumulated process-info per program (i.e. same name)
          -j  show cumulated process-info per container

          -C  sort processes in order of cpu consumption (default)
          -M  sort processes in order of memory consumption
          -D  sort processes in order of disk activity
          -N  sort processes in order of network activity
          -E  sort processes in order of GPU activity
          -A  sort processes in order of most active resource (auto mode)

        specific flags for raw logfiles:
          -w  write raw data to   file (compressed)
          -r  read  raw data from file (compressed)
              symbolic file: y[y...] for yesterday (repeated)
              file name '-': read raw data from stdin
          -S  finish atop automatically before midnight (i.s.o. #samples)
          -b  begin showing data from specified date/time
          -e  finish showing data after specified date/time

        interval: number of seconds   (minimum 0)
        samples:  number of intervals (minimum 1)

or with the keystroke 't' in interactive mode.

Please refer to the man-page of 'atop' for more details.
```
:o: Let service enable so it will start automatically on every reboot.

```R

=====================================================
root@biocolab-server:~# systemctl status atop
=====================================================
● atop.service - Atop advanced performance monitor
     Loaded: loaded (/lib/systemd/system/atop.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2023-08-25 04:06:00 UTC; 1h 20min ago
       Docs: man:atop(1)
    Process: 8866 ExecStartPre=/bin/sh -c test -n "$LOGINTERVAL" -a "$LOGINTERVAL" -eq "$LOGINTERVAL" (code=exited, status=0/SUCCESS)
    Process: 8867 ExecStartPre=/bin/sh -c test -n "$LOGGENERATIONS" -a "$LOGGENERATIONS" -eq "$LOGGENERATIONS" (code=exited, status=0/SUCCESS)
    Process: 8872 ExecStartPost=/usr/bin/find ${LOGPATH} -name atop_* -mtime +${LOGGENERATIONS} -exec rm -v {} ; (code=exited, status=0/SUCCESS)
   Main PID: 8870 (atop)
      Tasks: 1 (limit: 16759)
     Memory: 13.3M
        CPU: 1.062s
     CGroup: /system.slice/atop.service
             └─8870 /usr/bin/atop -R -w /var/log/atop/atop_20230825 600

Aug 25 04:06:00 biocolab-server systemd[1]: Starting Atop advanced performance monitor...
Aug 25 04:06:00 biocolab-server systemd[1]: Started Atop advanced performance monitor.
ith SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable atop
root@biocolab-server:~#

=====================================================
root@biocolab-server:~# systemctl enable atop
=====================================================
Synchronizing state of atop.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable atop
root@biocolab-server:~# 
```

:arrow_right: **By default atop was recorded on below location.**

```R
root@biocolab-server:/var/log/atop# pwd
/var/log/atop

root@biocolab-server:/var/log/atop# ls -lhrt
total 288K
-rw-r--r-- 1 root root 281K Aug 25 05:26 atop_20230825

```

:arrow_right: **Configuration.**

```R
root@biocolab-server:/var/log/atop# cat /etc/default/atop
# /etc/default/atop
# see man atoprc for more possibilities to configure atop execution

LOGOPTS="-R"
LOGINTERVAL=600
LOGGENERATIONS=28
LOGPATH=/var/log/atop
```

:arrow_right: **This interval is too long around 10 min. I would like to change it by 1 min.**

```R
# I did the changes on LOGINTERVAL=60
# Restart the atop service.

root@biocolab-server:/var/log/atop# cat /etc/default/atop
# /etc/default/atop
# see man atoprc for more possibilities to configure atop execution

LOGOPTS="-R"
LOGINTERVAL=60
LOGGENERATIONS=28
LOGPATH=/var/log/atop
root@biocolab-server:/var/log/atop#
root@biocolab-server:/var/log/atop# systemctl restart atop
root@biocolab-server:/var/log/atop# systemctl status atop
```
:arrow_right: **Command to read old log.**

```R
# atop -r <file name>

=====================================================
root@biocolab-server:/var/log/atop# pwd
/var/log/atop
root@biocolab-server:/var/log/atop# ls -lhrt
total 572K
-rw-r--r-- 1 root root 567K Aug 25 05:52 atop_20230825
root@biocolab-server:/var/log/atop#
=====================================================
root@biocolab-server:/var/log/atop# atop -r atop_20230825
root@biocolab-server:/var/log/atop#
```

<img alt="gcp" src="/pic/atopr.png" class="lazy" width="100%"> 

:o: Press **t** to read log based on time intervals.
:o: Press **ctrl + c** to exit from this window.

:arrow_right: We are having two ways to set up log rotation.
:one: logrotate
:two: cron

:eight_pointed_black_star: I would like to go with cron as I am only having only one process log to do something.

```R
# Here I used -1 because I want to less than 1 day. But we must give + value. like +3 to save disk space.

root@biocolab-server:/var/log/atop# find /var/log/atop/ -type f -name "atop_*" -mtime -1 -exec ls {} +
/var/log/atop/atop_20230825
root@biocolab-server:/var/log/atop# 

======================================================
Just for testing.
======================================================
root@biocolab-server:/var/log/atop# find /var/log/atop/ -type f -name "atop_*" -mtime -1 -exec gzip {} +
root@biocolab-server:/var/log/atop# ll
total 3752
drwxr-xr-x  2 root root      4096 Aug 25 06:57 ./
drwxrwxr-x 11 root syslog    4096 Aug 25 04:05 ../
-rw-r--r--  1 root root   1779812 Aug 25 06:56 atop_20230825.gz
root@biocolab-server:/var/log/atop#

root@biocolab-server:/var/log/atop# find /var/log/atop/ -type f -name "atop_*" -mtime -1 -exec rm {} +

======================================================
Remove.
======================================================
root@biocolab-server:/var/log/atop# ll
total 2012
drwxr-xr-x  2 root root      4096 Aug 25 06:58 ./
drwxrwxr-x 11 root syslog    4096 Aug 25 04:05 ../
root@biocolab-server:/var/log/atop#

```
:o: **To set up cron**
```R
# crontab -e
```

:o: **Below command to check cron job**

```R
root@biocolab-server:/var/log/atop# crontab -l
# Cron to run everyday midnight
# Compress
0 0 * * * find /var/log/atop/ -type f -name "atop_*" -mtime +1 -exec gzip {} +

# Removed old log
0 0 * * * find /var/log/atop/ -type f -name "atop_*.gz" -mtime +7 -exec rm {} +

```