# Anexo analisis memoria RAM

## Procesos activos 

### Pslist

```
OFFSET (V)      PID     TID     PPID    COMM    UID     GID     EUID    EGID    CREATION TIME   File output

0x88003d458000  1       1       0       systemd 0       0       0       0       2018-07-20 09:10:25.208000 UTC  Disabled
0x88003d458dc0  2       2       0       kthreadd        0       0       0       0       2018-07-20 09:10:25.208000 UTC  Disabled
0x88003d459b80  3       3       2       ksoftirqd/0     0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d45b700  5       5       2       kworker/0:0H    0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d45d280  7       7       2       rcu_sched       0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d45e040  8       8       2       rcu_bh  0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d45ee00  9       9       2       migration/0     0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d4c8000  10      10      2       watchdog/0      0       0       0       0       2018-07-20 09:10:25.260000 UTC  Disabled
0x88003d4fd280  11      11      2       kdevtmpfs       0       0       0       0       2018-07-20 09:10:25.276000 UTC  Disabled
0x88003d4fe040  12      12      2       netns   0       0       0       0       2018-07-20 09:10:25.292000 UTC  Disabled
0x88003d4fee00  13      13      2       perf    0       0       0       0       2018-07-20 09:10:25.300000 UTC  Disabled
0x88003d5a8000  14      14      2       xenwatch        0       0       0       0       2018-07-20 09:10:25.304000 UTC  Disabled
0x88003d5a8dc0  15      15      2       xenbus  0       0       0       0       2018-07-20 09:10:25.304000 UTC  Disabled
0x88003d5aa940  17      17      2       khungtaskd      0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d5ab700  18      18      2       writeback       0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d5ac4c0  19      19      2       ksmd    0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d5ad280  20      20      2       khugepaged      0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d5ae040  21      21      2       crypto  0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d5aee00  22      22      2       kintegrityd     0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d618000  23      23      2       bioset  0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d618dc0  24      24      2       kblockd 0       0       0       0       2018-07-20 09:10:25.328000 UTC  Disabled
0x88003d619b80  25      25      2       ata_sff 0       0       0       0       2018-07-20 09:10:25.608000 UTC  Disabled
0x88003d61a940  26      26      2       md      0       0       0       0       2018-07-20 09:10:25.620000 UTC  Disabled
0x88003d61b700  27      27      2       devfreq_wq      0       0       0       0       2018-07-20 09:10:25.624000 UTC  Disabled
0x88003d61e040  30      30      2       kswapd0 0       0       0       0       2018-07-20 09:10:26.006153 UTC  Disabled
0x88003d61ee00  31      31      2       vmstat  0       0       0       0       2018-07-20 09:10:26.006193 UTC  Disabled
0x88003d61d280  32      32      2       fsnotify_mark   0       0       0       0       2018-07-20 09:10:26.014598 UTC  Disabled
0x88003aea0000  33      33      2       ecryptfs-kthrea 0       0       0       0       2018-07-20 09:10:26.028379 UTC  Disabled
0x88003aeed280  49      49      2       kthrotld        0       0       0       0       2018-07-20 09:10:26.054316 UTC  Disabled
0x88003aeec4c0  50      50      2       bioset  0       0       0       0       2018-07-20 09:10:26.150156 UTC  Disabled
0x88003aeeb700  51      51      2       bioset  0       0       0       0       2018-07-20 09:10:26.150207 UTC  Disabled
0x88003aeea940  52      52      2       bioset  0       0       0       0       2018-07-20 09:10:26.150236 UTC  Disabled
0x88003aee9b80  53      53      2       bioset  0       0       0       0       2018-07-20 09:10:26.150264 UTC  Disabled
0x88003aee8dc0  54      54      2       bioset  0       0       0       0       2018-07-20 09:10:26.150292 UTC  Disabled
0x88003aee8000  55      55      2       bioset  0       0       0       0       2018-07-20 09:10:26.150317 UTC  Disabled
0x88003aeee040  56      56      2       bioset  0       0       0       0       2018-07-20 09:10:26.150344 UTC  Disabled
0x88003aeeee00  57      57      2       bioset  0       0       0       0       2018-07-20 09:10:26.150369 UTC  Disabled
0x88003aea6e00  58      58      2       bioset  0       0       0       0       2018-07-20 09:10:26.150396 UTC  Disabled
0x88003aea6040  59      59      2       bioset  0       0       0       0       2018-07-20 09:10:26.150421 UTC  Disabled
0x88003aea5280  60      60      2       bioset  0       0       0       0       2018-07-20 09:10:26.150448 UTC  Disabled
0x88003aea44c0  61      61      2       bioset  0       0       0       0       2018-07-20 09:10:26.150472 UTC  Disabled
0x88003aea3700  62      62      2       bioset  0       0       0       0       2018-07-20 09:10:26.150497 UTC  Disabled
0x88003aea2940  63      63      2       bioset  0       0       0       0       2018-07-20 09:10:26.150520 UTC  Disabled
0x88003aea1b80  64      64      2       bioset  0       0       0       0       2018-07-20 09:10:26.150572 UTC  Disabled
0x88003aea0dc0  65      65      2       bioset  0       0       0       0       2018-07-20 09:10:26.150599 UTC  Disabled
0x880036c08000  66      66      2       bioset  0       0       0       0       2018-07-20 09:10:26.155080 UTC  Disabled
0x880036c08dc0  67      67      2       bioset  0       0       0       0       2018-07-20 09:10:26.155212 UTC  Disabled
0x880036c09b80  68      68      2       bioset  0       0       0       0       2018-07-20 09:10:26.155324 UTC  Disabled
0x880036c0a940  69      69      2       bioset  0       0       0       0       2018-07-20 09:10:26.155435 UTC  Disabled
0x880036c0b700  70      70      2       bioset  0       0       0       0       2018-07-20 09:10:26.155552 UTC  Disabled
0x880036c0c4c0  71      71      2       bioset  0       0       0       0       2018-07-20 09:10:26.155666 UTC  Disabled
0x880036c0d280  72      72      2       bioset  0       0       0       0       2018-07-20 09:10:26.155780 UTC  Disabled
0x880036c0e040  73      73      2       bioset  0       0       0       0       2018-07-20 09:10:26.155896 UTC  Disabled
0x880036c0ee00  74      74      2       scsi_eh_0       0       0       0       0       2018-07-20 09:10:26.167527 UTC  Disabled
0x880036d10000  75      75      2       scsi_tmf_0      0       0       0       0       2018-07-20 09:10:26.167565 UTC  Disabled
0x880036d10dc0  76      76      2       scsi_eh_1       0       0       0       0       2018-07-20 09:10:26.172508 UTC  Disabled
0x880036d11b80  77      77      2       scsi_tmf_1      0       0       0       0       2018-07-20 09:10:26.172535 UTC  Disabled
0x880036d13700  79      79      2       bioset  0       0       0       0       2018-07-20 09:10:26.212303 UTC  Disabled
0x880036d16e00  83      83      2       ipv6_addrconf   0       0       0       0       2018-07-20 09:10:26.345338 UTC  Disabled
0x880036f66e00  96      96      2       deferwq 0       0       0       0       2018-07-20 09:10:26.400455 UTC  Disabled
0x880036f63700  258     258     2       raid5wq 0       0       0       0       2018-07-20 09:10:28.845488 UTC  Disabled
0x880036f90000  290     290     2       bioset  0       0       0       0       2018-07-20 09:10:28.908079 UTC  Disabled
0x880036f92940  314     314     2       jbd2/xvda1-8    0       0       0       0       2018-07-20 09:10:28.964272 UTC  Disabled
0x880036f93700  315     315     2       ext4-rsv-conver 0       0       0       0       2018-07-20 09:10:28.964312 UTC  Disabled
0x880036f66040  393     393     2       iscsi_eh        0       0       0       0       2018-07-20 09:10:29.787964 UTC  Disabled
0x88003a928dc0  399     399     2       ib_addr 0       0       0       0       2018-07-20 09:10:29.846471 UTC  Disabled
0x88003a92e040  405     405     2       ib_mcast        0       0       0       0       2018-07-20 09:10:29.881243 UTC  Disabled
0x880036f62940  407     407     2       ib_nl_sa_wq     0       0       0       0       2018-07-20 09:10:29.884918 UTC  Disabled
0x88003be18dc0  409     409     2       ib_cm   0       0       0       0       2018-07-20 09:10:29.888300 UTC  Disabled
0x88003be19b80  410     410     2       iw_cm_wq        0       0       0       0       2018-07-20 09:10:29.908276 UTC  Disabled
0x88003be1a940  411     411     2       rdma_cm 0       0       0       0       2018-07-20 09:10:29.916913 UTC  Disabled
0x88003be1c4c0  413     413     1       systemd-journal 0       0       0       0       2018-07-20 09:10:29.936519 UTC  Disabled
0x880036490000  417     417     2       kauditd 0       0       0       0       2018-07-20 09:10:30.006320 UTC  Disabled
0x880036f96e00  442     442     1       lvmetad 0       0       0       0       2018-07-20 09:10:30.111881 UTC  Disabled
0x880036496e00  471     471     1       systemd-udevd   0       0       0       0       2018-07-20 09:10:30.269674 UTC  Disabled
0x8800366f0000  560     560     1       systemd-timesyn 100     102     100     102     2018-07-20 09:10:30.776545 UTC  Disabled
0x88003be1ee00  582     582     2       kworker/0:1H    0       0       0       0       2018-07-20 09:10:30.909816 UTC  Disabled
0x880036492940  991     991     1       dhclient        0       0       0       0       2018-07-20 09:10:34.856410 UTC  Disabled
0x880036fdc4c0  1140    1140    1       iscsid  0       0       0       0       2018-07-20 09:10:36.173098 UTC  Disabled
0x880036fd9b80  1141    1141    1       iscsid  0       0       0       0       2018-07-20 09:10:36.173283 UTC  Disabled
0x880036496040  1148    1148    1       dbus-daemon     107     111     107     111     2018-07-20 09:10:36.214171 UTC  Disabled
0x88003a82d280  1166    1166    1       systemd-logind  0       0       0       0       2018-07-20 09:10:36.299061 UTC  Disabled
0x88003a82a940  1168    1168    1       rsyslogd        104     108     104     108     2018-07-20 09:10:36.302010 UTC  Disabled
0x88003a82c4c0  1172    1172    1       lxcfs   0       0       0       0       2018-07-20 09:10:36.309976 UTC  Disabled
0x880036491b80  1177    1177    1       cron    0       0       0       0       2018-07-20 09:10:36.322462 UTC  Disabled
0x88003a92b700  1182    1182    1       accounts-daemon 0       0       0       0       2018-07-20 09:10:36.344576 UTC  Disabled
0x88003be18000  1183    1183    1       atd     0       0       1       1       2018-07-20 09:10:36.347196 UTC  Disabled
0x880036f944c0  1197    1197    1       acpid   0       0       0       0       2018-07-20 09:10:36.384601 UTC  Disabled
0x880036f90dc0  1251    1251    1       mdadm   0       0       0       0       2018-07-20 09:10:36.609045 UTC  Disabled
0x88003bd88000  1310    1310    1       agetty  0       0       0       0       2018-07-20 09:10:36.833300 UTC  Disabled
0x88003bd8e040  1311    1311    1       agetty  0       0       0       0       2018-07-20 09:10:36.844866 UTC  Disabled
0x88003bd8c4c0  1340    1340    1       sshd    0       0       0       0       2018-07-20 09:10:37.096384 UTC  Disabled
0x8800364944c0  1506    1506    2       loop0   0       0       0       0       2018-07-20 09:10:42.785226 UTC  Disabled
0x88003c9744c0  1757    1757    2       loop1   0       0       0       0       2018-07-20 09:10:46.993843 UTC  Disabled
0x880036493700  1817    1817    1       amazon-ssm-agen 0       0       0       0       2018-07-20 09:10:47.392185 UTC  Disabled
0x88003a82b700  16817   16817   2       xfsalloc        0       0       0       0       2018-07-20 09:17:37.906158 UTC  Disabled
0x880036490dc0  16818   16818   2       xfs_mru_cache   0       0       0       0       2018-07-20 09:17:37.906651 UTC  Disabled
0x88003c976040  16956   16956   1       polkitd 0       0       0       0       2018-07-20 09:17:38.266905 UTC  Disabled
0x88000348ee00  27428   27428   1       apache2 0       0       0       0       2018-07-20 10:04:02.724797 UTC  Disabled
0x88003d45a940  28097   28097   2       loop2   0       0       0       0       2018-07-20 14:07:35.907074 UTC  Disabled
0x88003a928000  28103   28103   2       kworker/u30:2   0       0       0       0       2018-07-20 14:07:36.036753 UTC  Disabled
0x88003a92a940  28115   28115   1       snapd   0       0       0       0       2018-07-20 14:07:36.905661 UTC  Disabled
0x88003c970000  1811    1811    2       kworker/0:1     0       0       0       0       2018-07-22 06:30:03.632122 UTC  Disabled
0x880036fd8dc0  5573    5573    27428   apache2 33      33      33      33      2018-07-23 06:25:02.027052 UTC  Disabled
0x880036f91b80  5763    5763    27428   apache2 33      33      33      33      2018-07-23 06:50:13.697322 UTC  Disabled
0x88003c975280  6196    6196    27428   apache2 33      33      33      33      2018-07-23 10:26:46.767477 UTC  Disabled
0x88000348a940  6262    6262    27428   apache2 33      33      33      33      2018-07-23 10:51:35.362918 UTC  Disabled
0x88000348e040  6266    6266    27428   apache2 33      33      33      33      2018-07-23 10:51:54.387685 UTC  Disabled
0x8800366f6040  6281    6281    27428   apache2 33      33      33      33      2018-07-23 11:08:42.512891 UTC  Disabled
0x8800366f44c0  6285    6285    27428   apache2 33      33      33      33      2018-07-23 11:08:44.517880 UTC  Disabled
0x8800366f2940  6286    6286    27428   apache2 33      33      33      33      2018-07-23 11:08:44.518256 UTC  Disabled
0x880036f96040  6287    6287    27428   apache2 33      33      33      33      2018-07-23 11:08:44.518570 UTC  Disabled
0x88003a82e040  8254    8254    2       kworker/0:0     0       0       0       0       2018-07-24 00:46:54.157308 UTC  Disabled
0x880022832940  8520    8520    2       kworker/u30:0   0       0       0       0       2018-07-24 00:47:11.816145 UTC  Disabled
0x8800366f5280  9054    9054    27428   apache2 33      33      33      33      2018-07-24 05:18:49.670230 UTC  Disabled
0x8800366f6e00  9055    9055    1340    sshd    0       0       0       0       2018-07-24 05:24:16.058132 UTC  Disabled
0x8800366f3700  9057    9057    1       systemd 1000    1000    1000    1000    2018-07-24 05:24:18.533130 UTC  Disabled
0x88003bd8d280  9059    9059    2       kworker/0:2     0       0       0       0       2018-07-24 05:24:18.536275 UTC  Disabled
0x88003bd8b700  9060    9060    9057    (sd-pam)        1000    1000    1000    1000    2018-07-24 05:24:18.537639 UTC  Disabled
0x88003a829b80  9063    9063    2       kworker/0:3     0       0       0       0       2018-07-24 05:24:18.540133 UTC  Disabled
0x880022833700  9118    9118    9055    sshd    1000    1000    1000    1000    2018-07-24 05:24:18.705764 UTC  Disabled
0x880022830dc0  9126    9126    9118    bash    1000    1000    1000    1000    2018-07-24 05:24:19.275234 UTC  Disabled
0x88000348b700  14077   14077   2       kworker/u30:1   0       0       0       0       2018-07-24 05:25:49.462390 UTC  Disabled
0x88000348d280  14088   14088   9126    sudo    0       1000    0       1000    2018-07-24 05:27:03.805870 UTC  Disabled
0x880003488dc0  14089   14089   14088   insmod  0       0       0       0       2018-07-24 05:27:03.811245 UTC  Disabled
``` 

### Pstree

```
OFFSET (V)      PID     TID     PPID    COMM

0x88003d458000  1       1       0       systemd
* 0x88003be1c4c0        413     413     1       systemd-journal
* 0x880036f96e00        442     442     1       lvmetad
* 0x880036496e00        471     471     1       systemd-udevd
* 0x8800366f0000        560     560     1       systemd-timesyn
* 0x880036492940        991     991     1       dhclient
* 0x880036fdc4c0        1140    1140    1       iscsid
* 0x880036fd9b80        1141    1141    1       iscsid
* 0x880036496040        1148    1148    1       dbus-daemon
* 0x88003a82d280        1166    1166    1       systemd-logind
* 0x88003a82a940        1168    1168    1       rsyslogd
* 0x88003a82c4c0        1172    1172    1       lxcfs
* 0x880036491b80        1177    1177    1       cron
* 0x88003a92b700        1182    1182    1       accounts-daemon
* 0x88003be18000        1183    1183    1       atd
* 0x880036f944c0        1197    1197    1       acpid
* 0x880036f90dc0        1251    1251    1       mdadm
* 0x88003bd88000        1310    1310    1       agetty
* 0x88003bd8e040        1311    1311    1       agetty
* 0x88003bd8c4c0        1340    1340    1       sshd
** 0x8800366f6e00       9055    9055    1340    sshd
*** 0x880022833700      9118    9118    9055    sshd
**** 0x880022830dc0     9126    9126    9118    bash
***** 0x88000348d280    14088   14088   9126    sudo
****** 0x880003488dc0   14089   14089   14088   insmod
* 0x880036493700        1817    1817    1       amazon-ssm-agen
* 0x8800366f3700        9057    9057    1       systemd
** 0x88003bd8b700       9060    9060    9057    (sd-pam)
* 0x88003c976040        16956   16956   1       polkitd
* 0x88000348ee00        27428   27428   1       apache2
** 0x880036fd8dc0       5573    5573    27428   apache2
** 0x880036f91b80       5763    5763    27428   apache2
** 0x88003c975280       6196    6196    27428   apache2
** 0x88000348a940       6262    6262    27428   apache2
** 0x88000348e040       6266    6266    27428   apache2
** 0x8800366f6040       6281    6281    27428   apache2
** 0x8800366f44c0       6285    6285    27428   apache2
** 0x8800366f2940       6286    6286    27428   apache2
** 0x880036f96040       6287    6287    27428   apache2
** 0x8800366f5280       9054    9054    27428   apache2
* 0x88003a92a940        28115   28115   1       snapd
0x88003d458dc0  2       2       0       kthreadd
* 0x88003d459b80        3       3       2       ksoftirqd/0
* 0x88003d45b700        5       5       2       kworker/0:0H
* 0x88003d45d280        7       7       2       rcu_sched
* 0x88003d45e040        8       8       2       rcu_bh
* 0x88003d45ee00        9       9       2       migration/0
* 0x88003d4c8000        10      10      2       watchdog/0
* 0x88003d4fd280        11      11      2       kdevtmpfs
* 0x88003d4fe040        12      12      2       netns
* 0x88003d4fee00        13      13      2       perf
* 0x88003d5a8000        14      14      2       xenwatch
* 0x88003d5a8dc0        15      15      2       xenbus
* 0x88003d5aa940        17      17      2       khungtaskd
* 0x88003d5ab700        18      18      2       writeback
* 0x88003d5ac4c0        19      19      2       ksmd
* 0x88003d5ad280        20      20      2       khugepaged
* 0x88003d5ae040        21      21      2       crypto
* 0x88003d5aee00        22      22      2       kintegrityd
* 0x88003d618000        23      23      2       bioset
* 0x88003d618dc0        24      24      2       kblockd
* 0x88003d619b80        25      25      2       ata_sff
* 0x88003d61a940        26      26      2       md
* 0x88003d61b700        27      27      2       devfreq_wq
* 0x88003d61e040        30      30      2       kswapd0
* 0x88003d61ee00        31      31      2       vmstat
* 0x88003d61d280        32      32      2       fsnotify_mark
* 0x88003aea0000        33      33      2       ecryptfs-kthrea
* 0x88003aeed280        49      49      2       kthrotld
* 0x88003aeec4c0        50      50      2       bioset
* 0x88003aeeb700        51      51      2       bioset
* 0x88003aeea940        52      52      2       bioset
* 0x88003aee9b80        53      53      2       bioset
* 0x88003aee8dc0        54      54      2       bioset
* 0x88003aee8000        55      55      2       bioset
* 0x88003aeee040        56      56      2       bioset
* 0x88003aeeee00        57      57      2       bioset
* 0x88003aea6e00        58      58      2       bioset
* 0x88003aea6040        59      59      2       bioset
* 0x88003aea5280        60      60      2       bioset
* 0x88003aea44c0        61      61      2       bioset
* 0x88003aea3700        62      62      2       bioset
* 0x88003aea2940        63      63      2       bioset
* 0x88003aea1b80        64      64      2       bioset
* 0x88003aea0dc0        65      65      2       bioset
* 0x880036c08000        66      66      2       bioset
* 0x880036c08dc0        67      67      2       bioset
* 0x880036c09b80        68      68      2       bioset
* 0x880036c0a940        69      69      2       bioset
* 0x880036c0b700        70      70      2       bioset
* 0x880036c0c4c0        71      71      2       bioset
* 0x880036c0d280        72      72      2       bioset
* 0x880036c0e040        73      73      2       bioset
* 0x880036c0ee00        74      74      2       scsi_eh_0
* 0x880036d10000        75      75      2       scsi_tmf_0
* 0x880036d10dc0        76      76      2       scsi_eh_1
* 0x880036d11b80        77      77      2       scsi_tmf_1
* 0x880036d13700        79      79      2       bioset
* 0x880036d16e00        83      83      2       ipv6_addrconf
* 0x880036f66e00        96      96      2       deferwq
* 0x880036f63700        258     258     2       raid5wq
* 0x880036f90000        290     290     2       bioset
* 0x880036f92940        314     314     2       jbd2/xvda1-8
* 0x880036f93700        315     315     2       ext4-rsv-conver
* 0x880036f66040        393     393     2       iscsi_eh
* 0x88003a928dc0        399     399     2       ib_addr
* 0x88003a92e040        405     405     2       ib_mcast
* 0x880036f62940        407     407     2       ib_nl_sa_wq
* 0x88003be18dc0        409     409     2       ib_cm
* 0x88003be19b80        410     410     2       iw_cm_wq
* 0x88003be1a940        411     411     2       rdma_cm
* 0x880036490000        417     417     2       kauditd
* 0x88003be1ee00        582     582     2       kworker/0:1H
* 0x8800364944c0        1506    1506    2       loop0
* 0x88003c9744c0        1757    1757    2       loop1
* 0x88003c970000        1811    1811    2       kworker/0:1
* 0x88003a82e040        8254    8254    2       kworker/0:0
* 0x880022832940        8520    8520    2       kworker/u30:0
* 0x88003bd8d280        9059    9059    2       kworker/0:2
* 0x88003a829b80        9063    9063    2       kworker/0:3
* 0x88000348b700        14077   14077   2       kworker/u30:1
* 0x88003a82b700        16817   16817   2       xfsalloc
* 0x880036490dc0        16818   16818   2       xfs_mru_cache
* 0x88003d45a940        28097   28097   2       loop2
* 0x88003a928000        28103   28103   2       kworker/u30:2
```

## Historial de comandos de la consola

```
PID     Process CommandTime     Command

9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt install apache2 libapache2-mod-php php-mysql
9126    bash    2018-07-24 05:24:19.000000 UTC  ps -ef | grep apache
9126    bash    2018-07-24 05:24:19.000000 UTC  cd /etc/apache
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt update
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt upgrade
9126    bash    2018-07-24 05:24:19.000000 UTC  cd /etc/apache2
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:19.000000 UTC  cd sites-enabled/
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi 000-default.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi ../apache2.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  grep Listen ../*
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi ../ports.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt install mysql-client-core-5.7
9126    bash    2018-07-24 05:24:19.000000 UTC  cd html
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --authenticator webroot --installer apache --webroot-path /var/www/html -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  mysql -uadmin -p -hganga.ctmbcxcdb3us.eu-central-1.rds.amazonaws.com ganga
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo chown -R www-data:www-data wordpress
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --authenticator webroot --installer apache --webroot-path /var/www/html -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  mysql -u admin -p -h ganga.ctmbcxcdb3us.eu-central-1.rds.amazonaws.com
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l ../mods-enabled/
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo a2enmod ssl
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --authenticator webroot --installer apache --webroot-path /var/www/html -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-available/000-default.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --apache -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt-get install python-letsencrypt-apache
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --apache -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  letsencrypt
9126    bash    2018-07-24 05:24:19.000000 UTC  letsnecrypot
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt-get install python-certbot-apache
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo letsencrypt --apache -d ganga.site -d www.ganga.site
9126    bash    2018-07-24 05:24:19.000000 UTC  certbot
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  mysql -u admin -p -h ganga.ctmbcxcdb3us.eu-central-1.rds.amazonaws.com
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  apt-cache search certbot
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo rm index.html 
9126    bash    2018-07-24 05:24:19.000000 UTC  cd ..
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l ..
9126    bash    2018-07-24 05:24:19.000000 UTC  cd
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo tar xzf ~/wordpress-4.8.1.tar.gz 
9126    bash    2018-07-24 05:24:19.000000 UTC  ifconfig
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:19.000000 UTC  mysql -u ganga -p -h ganga.ctmbcxcdb3us.eu-central-1.rds.amazonaws.com
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  find /etc/apache2 -type f -exec grep -i Logformat {} \;
9126    bash    2018-07-24 05:24:19.000000 UTC  find /etc/apche2 -type f -exec grep -i Logformat {} \;
9126    bash    2018-07-24 05:24:19.000000 UTC  ls -l ~
9126    bash    2018-07-24 05:24:19.000000 UTC  mysql -uadmin -p -hganga.ctmbcxcdb3us.eu-central-1.rds.amazonaws.com ganga
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  history
9126    bash    2018-07-24 05:24:19.000000 UTC  find /etc/apache2 -type f -exec grep -Hi Logformat {} \;
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache restart
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  tail /var/log/apache2/access.log 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo apt install letsencrypt
9126    bash    2018-07-24 05:24:19.000000 UTC  cd /var/www/html
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:19.000000 UTC  exit
9126    bash    2018-07-24 05:24:19.000000 UTC  tail /var/log/apache2/access.log 
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo service apache2 restart
9126    bash    2018-07-24 05:24:19.000000 UTC  sudo vi /etc/apache2/sites-enabled/000-default-le-ssl.conf 
9126    bash    2018-07-24 05:24:31.000000 UTC  git clone https://github.com/504ensicsLabs/LiME.git
9126    bash    2018-07-24 05:24:36.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:39.000000 UTC  cd LiME/
9126    bash    2018-07-24 05:24:41.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:43.000000 UTC  cd src
9126    bash    2018-07-24 05:24:44.000000 UTC  ls -l
9126    bash    2018-07-24 05:24:45.000000 UTC  make
9126    bash    2018-07-24 05:24:49.000000 UTC  sudo ap install make
9126    bash    2018-07-24 05:24:53.000000 UTC  sudo apt install make
9126    bash    2018-07-24 05:24:59.000000 UTC  make
9126    bash    2018-07-24 05:25:09.000000 UTC  sudo apt install gcc
9126    bash    2018-07-24 05:25:21.000000 UTC  make
9126    bash    2018-07-24 05:25:46.000000 UTC  ls -l
9126    bash    2018-07-24 05:26:45.000000 UTC  sudo insmod lime-4.4.0-1061-aws.ko  "path=memoria.bin"
9126    bash    2018-07-24 05:26:57.000000 UTC  sudo insmod ./lime-4.4.0-1061-aws.ko  "path=memoria.bin"
9126    bash    2018-07-24 05:27:03.000000 UTC  sudo insmod ./lime-4.4.0-1061-aws.ko  "path=memoria.bin format=lime"
```

### Sockstat

```
NetNS   Process Name    PID     TID     FD      Sock Offset     Family  Type    Proto   Source Addr     Source Port     Destination Addr        Destination Port        State   Filter

4026531993      systemd 1       1       8       0x88003b422000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       1       group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd 1       1       14      0x88003700f000  AF_UNIX STREAM  -       /run/systemd/private    8788    -       -       LISTEN  -
4026531993      systemd 1       1       17      0x88003ab35000  AF_UNIX DGRAM   -       -       54269   /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      systemd 1       1       22      0x88003700f400  AF_UNIX DGRAM   -       /run/systemd/notify     8787    -       -       UNCONNECTED     -
4026531993      systemd 1       1       24      0x880036498800  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 13405   -       -       LISTEN  -
4026531993      systemd 1       1       25      0x88003649a800  AF_UNIX STREAM  -       /run/uuidd/request      13408   -       -       LISTEN  -
4026531993      systemd 1       1       26      0x8800154dd800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     54483   -       54482   ESTABLISHED     -
4026531993      systemd 1       1       29      0x88003b423000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000001       2313122220      group:0x00000000        0       UNCONNECTED     -
4026531993      systemd 1       1       30      0x8800366b7800  AF_UNIX STREAM  -       /run/acpid.socket       13398   -       -       LISTEN  -
4026531993      systemd 1       1       31      0x88003700ec00  AF_UNIX DGRAM   -       /run/systemd/journal/syslog     8794    -       -       UNCONNECTED     -
4026531993      systemd 1       1       33      0x88003cd52400  AF_UNIX STREAM  -       /run/systemd/journal/stdout     110298  -       110294  ESTABLISHED     -
4026531993      systemd 1       1       34      0x88003bf9fc00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     9631    -       9630    ESTABLISHED     -
4026531993      systemd 1       1       35      0x8800364b3800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     10165   -       10164   ESTABLISHED     -
4026531993      systemd 1       1       36      0x8800366b4c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     11050   -       11049   ESTABLISHED     -
4026531993      systemd 1       1       37      0x8800366c1000  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15855   -       13696   ESTABLISHED     -
4026531993      systemd 1       1       38      0x8800364ed000  AF_NETLINK      RAW     NETLINK_AUDIT   -       2930670031      group:0x00000000        0       UNCONNECTED     -
4026531993      systemd 1       1       39      0x880036532c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15862   -       13794   ESTABLISHED     -
4026531993      systemd 1       1       40      0x880036701000  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15863   -       13932   ESTABLISHED     -
4026531993      systemd 1       1       41      0x880036706c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15875   -       14003   ESTABLISHED     -
4026531993      systemd 1       1       42      0x88003ca4ac00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15882   -       14145   ESTABLISHED     -
4026531993      systemd 1       1       43      0x880036534800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15916   -       15791   ESTABLISHED     -
4026531993      systemd 1       1       47      0x88003ac83c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     17778   -       17777   ESTABLISHED     -
4026531993      systemd 1       1       52      0x8800366c1400  AF_UNIX STREAM  -       -       13697   /var/run/dbus/system_bus_socket 13735   ESTABLISHED     -
4026531993      systemd 1       1       53      0x88003a904c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     8804    -       -       LISTEN  -
4026531993      systemd 1       1       54      0x88003a905000  AF_UNIX DGRAM   -       /run/systemd/journal/socket     8805    -       -       UNCONNECTED     -
4026531993      systemd 1       1       55      0x88003700e400  AF_UNIX SEQPACKET       -       /run/udev/control       8793    -       -       UNCONNECTED     -
4026531993      systemd 1       1       56      0x880036d96400  AF_UNIX STREAM  -       /run/lvm/lvmpolld.socket        8802    -       -       LISTEN  -
4026531993      systemd 1       1       57      0x8800364ec000  AF_NETLINK      RAW     NETLINK_AUDIT   groups:0x00000001       1       group:0x00000000        0       UNCONNECTED     -
4026531993      systemd 1       1       60      0x880036d96000  AF_UNIX DGRAM   -       /run/systemd/journal/dev-log    8801    -       -       UNCONNECTED     -
4026531993      systemd 1       1       61      0x8800366b5400  AF_UNIX STREAM  -       /var/lib/lxd/unix.socket        13397   -       -       LISTEN  -
4026531993      systemd 1       1       84      0x88003dd9dc00  AF_UNIX STREAM  -       /run/lvm/lvmetad.socket 8800    -       -       LISTEN  -
4026531993      systemd 1       1       86      0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      systemd 1       1       87      0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      systemd-journal 413     413     3       0x88003a904c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     8804    -       -       LISTEN  -
4026531993      systemd-journal 413     413     4       0x88003a905000  AF_UNIX DGRAM   -       /run/systemd/journal/socket     8805    -       -       UNCONNECTED     -
4026531993      systemd-journal 413     413     5       0x8800364ec000  AF_NETLINK      RAW     NETLINK_AUDIT   groups:0x00000001       1       group:0x00000000        0       UNCONNECTED     -
4026531993      systemd-journal 413     413     6       0x880036d96000  AF_UNIX DGRAM   -       /run/systemd/journal/dev-log    8801    -       -       UNCONNECTED     -
4026531993      systemd-journal 413     413     14      0x88003be5ec00  AF_UNIX DGRAM   -       -       9345    /run/systemd/notify     8787    UNCONNECTED     -
4026531993      systemd-journal 413     413     17      0x88003bf9fc00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     9631    -       9630    ESTABLISHED     -
4026531993      systemd-journal 413     413     18      0x8800364b3800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     10165   -       10164   ESTABLISHED     -
4026531993      systemd-journal 413     413     19      0x880036532c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15862   -       13794   ESTABLISHED     -
4026531993      systemd-journal 413     413     20      0x880036701000  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15863   -       13932   ESTABLISHED     -
4026531993      systemd-journal 413     413     21      0x8800366c1000  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15855   -       13696   ESTABLISHED     -
4026531993      systemd-journal 413     413     22      0x8800366b4c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     11050   -       11049   ESTABLISHED     -
4026531993      systemd-journal 413     413     23      0x880036706c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15875   -       14003   ESTABLISHED     -
4026531993      systemd-journal 413     413     24      0x88003ac83c00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     17778   -       17777   ESTABLISHED     -
4026531993      systemd-journal 413     413     25      0x88003ca4ac00  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15882   -       14145   ESTABLISHED     -
4026531993      systemd-journal 413     413     26      0x8800154dd800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     54483   -       54482   ESTABLISHED     -
4026531993      systemd-journal 413     413     27      0x88003cd52400  AF_UNIX STREAM  -       /run/systemd/journal/stdout     110298  -       110294  ESTABLISHED     -
4026531993      systemd-journal 413     413     29      0x880036534800  AF_UNIX STREAM  -       /run/systemd/journal/stdout     15916   -       15791   ESTABLISHED     -
4026531993      lvmetad 442     442     1       0x88003647fc00  AF_UNIX STREAM  -       -       9630    /run/systemd/journal/stdout     9631    ESTABLISHED     -
4026531993      lvmetad 442     442     2       0x88003647fc00  AF_UNIX STREAM  -       -       9630    /run/systemd/journal/stdout     9631    ESTABLISHED     -
4026531993      lvmetad 442     442     3       0x88003dd9dc00  AF_UNIX STREAM  -       /run/lvm/lvmetad.socket 8800    -       -       LISTEN  -
4026531993      systemd-udevd   471     471     1       0x8800364b2000  AF_UNIX STREAM  -       -       10164   /run/systemd/journal/stdout     10165   ESTABLISHED     -
4026531993      systemd-udevd   471     471     2       0x8800364b2000  AF_UNIX STREAM  -       -       10164   /run/systemd/journal/stdout     10165   ESTABLISHED     -
4026531993      systemd-udevd   471     471     3       0x88003b423000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000001       2313122220      group:0x00000000        0       UNCONNECTED     -
4026531993      systemd-udevd   471     471     4       0x88003700e400  AF_UNIX SEQPACKET       -       /run/udev/control       8793    -       -       UNCONNECTED     -
4026531993      systemd-udevd   471     471     5       0x88003a8ad000  AF_UNIX DGRAM   -       -       10169   /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      systemd-udevd   471     471     7       0x88003c885000  AF_UNIX DGRAM   -       -       10189   -       10190   UNCONNECTED     -
4026531993      systemd-udevd   471     471     8       0x88003c880c00  AF_UNIX DGRAM   -       -       10190   -       10189   UNCONNECTED     -
4026531993      systemd-timesyn 560     560     1       0x8800366b2c00  AF_UNIX STREAM  -       -       11049   /run/systemd/journal/stdout     11050   ESTABLISHED     -
4026531993      systemd-timesyn 560     560     2       0x8800366b2c00  AF_UNIX STREAM  -       -       11049   /run/systemd/journal/stdout     11050   ESTABLISHED     -
4026531993      systemd-timesyn 560     560     3       0x88003a940800  AF_UNIX DGRAM   -       -       11111   /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      systemd-timesyn 560     560     7       0x88003a945000  AF_UNIX DGRAM   -       -       11115   -       11116   UNCONNECTED     -
4026531993      systemd-timesyn 560     560     8       0x88003a942400  AF_UNIX DGRAM   -       -       11116   -       11115   UNCONNECTED     -
4026531993      systemd-timesyn 560     560     9       0x88003a945c00  AF_UNIX DGRAM   -       -       11117   -       11118   UNCONNECTED     -
4026531993      systemd-timesyn 560     560     10      0x88003a940400  AF_UNIX DGRAM   -       -       11118   -       11117   UNCONNECTED     -
4026531993      sd-resolve      560     566     1       0x8800366b2c00  AF_UNIX STREAM  -       -       11049   /run/systemd/journal/stdout     11050   ESTABLISHED     -
4026531993      sd-resolve      560     566     2       0x8800366b2c00  AF_UNIX STREAM  -       -       11049   /run/systemd/journal/stdout     11050   ESTABLISHED     -
4026531993      sd-resolve      560     566     3       0x88003a940800  AF_UNIX DGRAM   -       -       11111   /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      sd-resolve      560     566     7       0x88003a945000  AF_UNIX DGRAM   -       -       11115   -       11116   UNCONNECTED     -
4026531993      sd-resolve      560     566     8       0x88003a942400  AF_UNIX DGRAM   -       -       11116   -       11115   UNCONNECTED     -
4026531993      sd-resolve      560     566     9       0x88003a945c00  AF_UNIX DGRAM   -       -       11117   -       11118   UNCONNECTED     -
4026531993      sd-resolve      560     566     10      0x88003a940400  AF_UNIX DGRAM   -       -       11118   -       11117   UNCONNECTED     -
4026531993      dhclient        991     991     3       0x88003731a400  AF_UNIX DGRAM   -       -       12776   /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      dhclient        991     991     5       0x880036465000  AF_PACKET       RAW     ETH_P_ALL       eth0    -       -       -       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      dhclient        991     991     6       0x88003cc883c0  AF_INET DGRAM   UDP     0.0.0.0 68      0.0.0.0 0       UNCONNECTED     -
4026531993      iscsid  1140    1140    4       0x88003649d400  AF_UNIX DGRAM   -       -       13502   /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      iscsid  1141    1141    3       0x88003be59c00  AF_UNIX DGRAM   -       -       13495   /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      iscsid  1141    1141    4       0x880036558000  AF_UNIX STREAM  -               13496   -       -       LISTEN  -
4026531993      iscsid  1141    1141    6       0x880036461800  AF_NETLINK      RAW     NETLINK_ISCSI   groups:0x00000001       1141    group:0x00000000,lkm:scsi_transport_iscsi       0       UNCONNECTED     -
4026531993      dbus-daemon     1148    1148    1       0x8800366c0c00  AF_UNIX STREAM  -       -       13696   /run/systemd/journal/stdout     15855   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    2       0x8800366c0c00  AF_UNIX STREAM  -       -       13696   /run/systemd/journal/stdout     15855   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    3       0x880036498800  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 13405   -       -       LISTEN  -
4026531993      dbus-daemon     1148    1148    5       0x8800366c5000  AF_UNIX DGRAM   -       -       13730   /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      dbus-daemon     1148    1148    7       0x880036464800  AF_NETLINK      RAW     NETLINK_AUDIT   -       0       group:0x00000000        0       UNCONNECTED     -
4026531993      dbus-daemon     1148    1148    8       0x8800366c3400  AF_UNIX STREAM  -       -       13733   -       13734   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    9       0x8800366c5c00  AF_UNIX STREAM  -       -       13734   -       13733   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    10      0x8800366c1800  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 13735   -       13697   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    11      0x88003b647c00  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 13870   -       13869   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    12      0x88003b631800  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 14834   -       14766   ESTABLISHED     -
4026531993      dbus-daemon     1148    1148    13      0x88003bc4fc00  AF_UNIX STREAM  -       /var/run/dbus/system_bus_socket 32769   -       32768   ESTABLISHED     -
4026531993      systemd-logind  1166    1166    1       0x880036532800  AF_UNIX STREAM  -       -       13794   /run/systemd/journal/stdout     15862   ESTABLISHED     -
4026531993      systemd-logind  1166    1166    2       0x880036532800  AF_UNIX STREAM  -       -       13794   /run/systemd/journal/stdout     15862   ESTABLISHED     -
4026531993      systemd-logind  1166    1166    3       0x88003b644400  AF_UNIX DGRAM   -       -       13860   /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      systemd-logind  1166    1166    8       0x880036465800  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       1166    group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd-logind  1166    1166    9       0x880036460000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       2182494999      group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd-logind  1166    1166    10      0x880036462000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       2430890161      group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd-logind  1166    1166    11      0x880036460800  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       2915434994      group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd-logind  1166    1166    12      0x88003b647800  AF_UNIX STREAM  -       -       13869   /var/run/dbus/system_bus_socket 13870   ESTABLISHED     -
4026531993      rsyslogd        1168    1168    3       0x88003700ec00  AF_UNIX DGRAM   -       /run/systemd/journal/syslog     8794    -       -       UNCONNECTED     -
4026531993      in:imuxsock     1168    1212    3       0x88003700ec00  AF_UNIX DGRAM   -       /run/systemd/journal/syslog     8794    -       -       UNCONNECTED     -
4026531993      in:imklog       1168    1213    3       0x88003700ec00  AF_UNIX DGRAM   -       /run/systemd/journal/syslog     8794    -       -       UNCONNECTED     -
4026531993      rs:main Q:Reg   1168    1214    3       0x88003700ec00  AF_UNIX DGRAM   -       /run/systemd/journal/syslog     8794    -       -       UNCONNECTED     -
4026531993      lxcfs   1172    1172    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    1172    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    1735    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    1735    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5609    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5609    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5614    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5614    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5617    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5617    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5618    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5618    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5622    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5622    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5623    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5623    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5624    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5624    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5625    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5625    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5626    1       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      lxcfs   1172    5626    2       0x880036700c00  AF_UNIX STREAM  -       -       13932   /run/systemd/journal/stdout     15863   ESTABLISHED     -
4026531993      cron    1177    1177    1       0x880036706800  AF_UNIX STREAM  -       -       14003   /run/systemd/journal/stdout     15875   ESTABLISHED     -
4026531993      cron    1177    1177    2       0x880036706800  AF_UNIX STREAM  -       -       14003   /run/systemd/journal/stdout     15875   ESTABLISHED     -
4026531993      accounts-daemon 1182    1182    1       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      accounts-daemon 1182    1182    2       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      accounts-daemon 1182    1182    5       0x88003b631400  AF_UNIX STREAM  -       -       14766   /var/run/dbus/system_bus_socket 14834   ESTABLISHED     -
4026531993      gmain   1182    1232    1       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      gmain   1182    1232    2       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      gmain   1182    1232    5       0x88003b631400  AF_UNIX STREAM  -       -       14766   /var/run/dbus/system_bus_socket 14834   ESTABLISHED     -
4026531993      gdbus   1182    1237    1       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      gdbus   1182    1237    2       0x88003ca4a800  AF_UNIX STREAM  -       -       14145   /run/systemd/journal/stdout     15882   ESTABLISHED     -
4026531993      gdbus   1182    1237    5       0x88003b631400  AF_UNIX STREAM  -       -       14766   /var/run/dbus/system_bus_socket 14834   ESTABLISHED     -
4026531993      acpid   1197    1197    0       0x8800366b7800  AF_UNIX STREAM  -       /run/acpid.socket       13398   -       -       LISTEN  -
4026531993      acpid   1197    1197    3       0x88003bc96400  AF_UNIX DGRAM   -       -       14427   /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      acpid   1197    1197    8       0x880036463800  AF_NETLINK      RAW     NETLINK_GENERIC groups:0x00000002       1197    group:0x00000000        0       UNCONNECTED     -
4026531993      sshd    1340    1340    1       0x880036530c00  AF_UNIX STREAM  -       -       15791   /run/systemd/journal/stdout     15916   ESTABLISHED     -
4026531993      sshd    1340    1340    2       0x880036530c00  AF_UNIX STREAM  -       -       15791   /run/systemd/journal/stdout     15916   ESTABLISHED     -
4026531993      sshd    1340    1340    3       0x8800367e0780  AF_INET STREAM  TCP     0.0.0.0 22      0.0.0.0 0       LISTEN  -
4026531993      sshd    1340    1340    4       0x8800367e8000  AF_INET6        STREAM  TCP     ::      22      ::      0       LISTEN  -
4026531993      amazon-ssm-agen 1817    1817    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1817    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1836    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1836    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1837    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1837    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1838    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1838    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1845    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1845    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1856    1       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      amazon-ssm-agen 1817    1856    2       0x88003ac80c00  AF_UNIX STREAM  -       -       17777   /run/systemd/journal/stdout     17778   ESTABLISHED     -
4026531993      polkitd 16956   16956   6       0x88003bc49400  AF_UNIX STREAM  -       -       32768   /var/run/dbus/system_bus_socket 32769   ESTABLISHED     -
4026531993      gmain   16956   16958   6       0x88003bc49400  AF_UNIX STREAM  -       -       32768   /var/run/dbus/system_bus_socket 32769   ESTABLISHED     -
4026531993      gdbus   16956   16960   6       0x88003bc49400  AF_UNIX STREAM  -       -       32768   /var/run/dbus/system_bus_socket 32769   ESTABLISHED     -
4026531993      apache2 27428   27428   3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 27428   27428   4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 27428   27428   5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 27428   27428   6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      snapd   28115   28115   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28115   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28115   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28115   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28118   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28118   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28118   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28118   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28119   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28119   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28119   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28119   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28120   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28120   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28120   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28120   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28122   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28122   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28122   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28122   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28130   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28130   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28130   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28130   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      snapd   28115   28131   1       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28131   2       0x8800154de000  AF_UNIX STREAM  -       -       54482   /run/systemd/journal/stdout     54483   ESTABLISHED     -
4026531993      snapd   28115   28131   7       0x88003bcdb800  AF_UNIX STREAM  -       /run/snapd.socket       26985   -       -       LISTEN  -
4026531993      snapd   28115   28131   9       0x88003bcd8000  AF_UNIX STREAM  -       /run/snapd-snap.socket  26986   -       -       LISTEN  -
4026531993      apache2 5573    5573    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 5573    5573    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 5573    5573    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 5573    5573    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 5763    5763    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 5763    5763    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 5763    5763    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 5763    5763    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6196    6196    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6196    6196    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6196    6196    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6196    6196    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6262    6262    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6262    6262    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6262    6262    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6262    6262    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6266    6266    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6266    6266    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6266    6266    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6266    6266    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6281    6281    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6281    6281    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6281    6281    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6281    6281    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6285    6285    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6285    6285    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6285    6285    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6285    6285    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6286    6286    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6286    6286    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6286    6286    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6286    6286    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 6287    6287    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6287    6287    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 6287    6287    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 6287    6287    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      apache2 9054    9054    3       0x8800367e0000  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 9054    9054    4       0x8800367e8840  AF_INET6        STREAM  TCP     ::      80      ::      0       LISTEN  -
4026531993      apache2 9054    9054    5       0x8800367e1e00  AF_INET STREAM  TCP     0.0.0.0 0       0.0.0.0 0       CLOSE   -
4026531993      apache2 9054    9054    6       0x8800367e9080  AF_INET6        STREAM  TCP     ::      443     ::      0       LISTEN  -
4026531993      sshd    9055    9055    3       0x8800367e1680  AF_INET STREAM  TCP     172.31.47.60    22      23.226.128.37   42760   ESTABLISHED     -
4026531993      sshd    9055    9055    4       0x88003cd51c00  AF_UNIX DGRAM   -       -       110219  /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      sshd    9055    9055    6       0x88003cd50800  AF_UNIX STREAM  -       -       110388  -       110387  ESTABLISHED     -
4026531993      systemd 9057    9057    1       0x88003cd55400  AF_UNIX STREAM  -       -       110294  /run/systemd/journal/stdout     110298  ESTABLISHED     -
4026531993      systemd 9057    9057    2       0x88003cd55400  AF_UNIX STREAM  -       -       110294  /run/systemd/journal/stdout     110298  ESTABLISHED     -
4026531993      systemd 9057    9057    3       0x88003cd52000  AF_UNIX DGRAM   -       -       110320  /run/systemd/journal/socket     8805    UNCONNECTED     -
4026531993      systemd 9057    9057    8       0x88003ac62000  AF_NETLINK      RAW     NETLINK_KOBJECT_UEVENT  groups:0x00000002       9057    group:0x00000000        0       UNCONNECTED     filter_type=socket_filter,bpf_filter_type=cBPF
4026531993      systemd 9057    9057    13      0x88003cd54400  AF_UNIX DGRAM   -       /run/user/1000/systemd/notify   110333  -       -       UNCONNECTED     -
4026531993      systemd 9057    9057    14      0x88003cd56800  AF_UNIX STREAM  -       /run/user/1000/systemd/private  110334  -       -       LISTEN  -
4026531993      (sd-pam)        9060    9060    1       0x88003cd55400  AF_UNIX STREAM  -       -       110294  /run/systemd/journal/stdout     110298  ESTABLISHED     -
4026531993      (sd-pam)        9060    9060    2       0x88003cd55400  AF_UNIX STREAM  -       -       110294  /run/systemd/journal/stdout     110298  ESTABLISHED     -
4026531993      (sd-pam)        9060    9060    7       0x88003cd53c00  AF_UNIX DGRAM   -       -       110301  /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      sshd    9118    9118    3       0x8800367e1680  AF_INET STREAM  TCP     172.31.47.60    22      23.226.128.37   42760   ESTABLISHED     -
4026531993      sshd    9118    9118    4       0x88003cd51c00  AF_UNIX DGRAM   -       -       110219  /run/systemd/journal/dev-log    8801    UNCONNECTED     -
4026531993      sshd    9118    9118    5       0x88003cd55c00  AF_UNIX STREAM  -       -       110387  -       110388  ESTABLISHED     -
4026531993      sudo    14088   14088   3       0x880015404800  AF_UNIX STREAM  -       -       116630  -       0       ESTABLISHED     -
4026531993      sudo    14088   14088   5       0x880017bf2000  AF_NETLINK      RAW     NETLINK_AUDIT   -       14088   group:0x00000000        0       UNCONNECTED     -
4026531993      sudo    14088   14088   8       0x880015403000  AF_UNIX DGRAM   -       -       116633  /run/systemd/journal/dev-log    8801    UNCONNECTED     -
```

