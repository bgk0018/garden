---
{"dg-publish":true,"dg-path":"articles/2025-01-11 - Home Server Catastrophic Failure Review/Restore backup failure (zstd decompression).md","permalink":"/articles/2025-01-11-home-server-catastrophic-failure-review/restore-backup-failure-zstd-decompression/","title":"Restore backup failure (zstd decompression)","tags":["📰"],"created":"2025-01-14T09:40:38.013-06:00","updated":"2025-01-11T17:38:53.000-06:00"}
---


# Restore Backup Failure (zstd decompression)

## Concepts

| Name | Weight |
| ---- | ------ |

{ .block-language-dataview}

>[!summary]- Description

## Content

- - [#1](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-332905)

Hello,

I created backups for all of my VMs on a nfsshare and wanted to restore them. The majority succeeded without any problems but for 3 as far as I know it fails on decompressing with *Decoding error (36) : Restored data doesn't match checksum*

I'm not that confident anymore that I can recover the data, but maybe smn can help me here.

[![Hannes Laimer](https://forum.proxmox.com/data/avatars/s/97/97843.jpg?1598337747)](https://forum.proxmox.com/members/hannes-laimer.97843/)

- - [#2](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-333129)

Hey,  
could you post the output log?

- - [#3](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-333170)

Thats the error

Code:

```
progress 99% (read 106300440576 bytes, duration 894 sec)
_18-21_48_56.vma.zst : Decoding error (36) : Restored data doesn't match checksum 
progress 100% (read 107374182400 bytes, duration 898 sec)
total bytes read 107374182400, sparse bytes 2547867648 (2.37%)
space reduction due to 4K zero blocks 0.909%
temporary volume 'local:109/vm-109-disk-0.qcow2' sucessfuly removed
no lock found trying to remove 'create' lock
TASK ERROR: command 'set -o pipefail && zstd -q -d -c /mnt/pve/backup/dump/vzdump-qemu-105-2020_08_18-21_48_56.vma.zst | vma extract -v -r /var/tmp/vzdumptmp8492.fifo - /var/tmp/vzdumptmp8492' failed: exit code 1
```

[![Hannes Laimer](https://forum.proxmox.com/data/avatars/s/97/97843.jpg?1598337747)](https://forum.proxmox.com/members/hannes-laimer.97843/)

- - [#4](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-333181)

Could you try to verify the .vma file with:

Code:

```
unzstd /mnt/pve/backup/dump/vzdump-qemu-105-2020_08_18-21_48_56.vma.zst
vma verify /mnt/pve/backup/dump/vzdump-qemu-105-2020_08_18-21_48_56.vma -v
```

then post the output here

- - [#5](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-333186)

It's already failing at the decompression and deletes the file. I wrote the failing content to another file and the verification fails at 99% with

Code:

```
vma: verify failed - read short extent (506 bytes)
Trace/breakpoint trap
```

[![Hannes Laimer](https://forum.proxmox.com/data/avatars/s/97/97843.jpg?1598337747)](https://forum.proxmox.com/members/hannes-laimer.97843/)

- - [#7](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-333192)

Yeah already read that, but that didn't really help.

Thanks anyways.

- - [#8](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-336566)

have the same problem, any solution????

- - [#9](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-336568)

@zIvalid I found an alternative, instead compress with ZSTD, I did with GZIP and be able restore it =)

- - [#10](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-400479)

For anyone searching and finding this thread, I ran into this same problem.  
Mine was even more trivial, as I actually had an backup image that I created \*and\* test restored successfully.

I then reloaded Proxmox from scratch, to adjust a few things (partitions-wise) on my drives.  
When I went to restore the backup I had literally created (and test restored!) just a few hours before, I got the error this thread is mentioning!

The image always failed during the unzstd, with the same "*Decoding error (36) : Restored data doesn't match checksum" error.*  
Clearly I knew my image was fine, so I investigated a bit more.  
I took the image and dumped it to my Windows box running cygwin, which also has unzstd installed.

Running in through that unstzd worked fine!

PS: The cygwin version of unstzd that worked was:  
$ unzstd --version  
\*\*\* zstd command line interface 64-bits v1.4.5, by Yann Collet \*\*\*

My Proxmox 6.4-9 version of unstzd is far older for some reason:  
root@proxmoxve:~# unzstd --version  
\*\*\* zstd command line interface 64-bits v1.3.8, by Yann Collet \*\*\*

I have no idea why the Proxmox version is so old, I just checked Ubuntu 20.04, and it is v1.4.4.

Anyway, long story short, for those finding this thread with this error, try to find another system that has a newer unstdz, uncompress it there, then upload that uncompressed image back up to Proxmox.  
That uncompressed image should work just fine.

- - [#11](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-449610)

I encountered the same issue today on a 116GB backup file.

The backup was taken with ZSTD on Proxmox 7.1-10 (over to a CIFS mounted storage on a TrueNAS server) and I couldn't restore it, tried a few times. I tried an older backup of the same LXC, same issue. Re-did the backup using ZSTD, it finished (like all others) successfully and same issue again, couldn't restore it. All the the other backups finished successfully as well. Restore of backups for other VMs and LXCs are working, I tested all the other ZSTD backups, only this one failed to restore every time. This is the largest backup I have, all the other VMs and LXCs backups are 37GB or less but this one is 116GB.

I ended up changing the backup from ZSTD to GZIP and I was able to restore this new backup without any issue on the first try.

Googling this error, you can see that a lot of people also encounter this issue every now and then. Many of them never find the root cause.

This is the second time this issue happens to me with ZSTD. I cannot depend on something that doesn't work 100% of the time, especially for backups and especially when it says that the backup finished successfully. Backups are usually the last resort before total data loss so I'm going back to gzip for now until I can or someone else can figure out what is going on. So far, fingers crossed, gzip never failed me.

In the meantime, make sure to test your backups every now and then ![:)](https://cdn.jsdelivr.net/joypixels/assets/8.0/png/unicode/64/1f642.png "Smile :)")

- - [#12](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-481232)

Hi,

I'm facing the same issue.

I was able to get the tar with the zstd nocheck option

unzstd -d --no-check vzdump-lxc-\*\*\*.tar.zst

then extract the tar without any issue with cpio

cpio -ivd -H tar < vzdump-lxc-\*\*\*.tar

But how can I recompress and restore this? Please hint me to some guide if available.1  
edit: nevermind, extracted the necessary config and data files and created a new container

Last edited: Jul 1, 2022

- - [#13](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-490100)

Same problem here ![:(](https://cdn.jsdelivr.net/joypixels/assets/8.0/png/unicode/64/1f641.png "Frown :("). I started having the problem when I bought a mini pc with NVME SSD. Until I used Proxmox with NVME, I never encountered the problem. I don't know if it's necessarily related, but...

- - [#14](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-490331)

After investigating the problem for a large part of the day, I have the following conclusions:  
\- My mini PC works fine (MINISFORUM X35G). I tested its RAM memory with memtest86. It lasted 4 hours and 40 minutes. The RAM memory problem mentioned in other posts is eliminated.  
\- I tested the ".zst" backup on a Windows machine with the peazip-8.7.0 tool. Is OK. I even unzipped the backup.  
\- I tried to restore several times with the same backup and the error never appears at the same point. Once it appears at 80%, once at 40%, once at 99%, once at 4%, once at 55%. This makes me still believe that the archive is fine.  
\- In my case, the problem is in Proxmox (7.2-7) when restoring the backup.

Solution  
\- I copied the ".zst" file to a Windows machine  
\- I unzipped the file with the peazip-8.7.0 tool  
\- I copied back the unzipped backup on the shared path to which Proxmox also has access (I use OpenMediaVault)  
\- I restored directly from the unzipped backup  
\- Everything worked.

- - [#15](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-590658)

The same issue for me, no restore has worked from the GUI, ever, due to the checksum error...and it's been driving me crazy. The solution was similar for me as above. I didn't have to copy the zst to another computer, I instead just used the --no-check flag when manually decompressing with unzstd in a normal shell session. I then restored the uncompressed backup with the GUI and it worked. First successful restore in the 2 years i've been using Proxmox

- - [#16](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-611815)

> The same issue for me, no restore has worked from the GUI, ever, due to the checksum error...and it's been driving me crazy. The solution was similar for me as above. I didn't have to copy the zst to another computer, I instead just used the --no-check flag when manually decompressing with unzstd in a normal shell session. I then restored the uncompressed backup with the GUI and it worked. First successful restore in the 2 years i've been using Proxmox

Only your version worked for me. File size 40GB. THX

- - [#17](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-611949)

Please: TEST your backups after the backup has been done. A backup, that is not tested, is worth nothing and yields to the problems you all describe. Restore tests are crucial and are - depending on where you life - required my GDPR.  
For easier backup verification, consider using Proxmox Backup Server, which can do that automatically.

- - [#18](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-648990)

> A similar problem was already reported once, it turned out to be a faulty RAM. Maybe try what was mentioned in the other thread.
> 
> [https://forum.proxmox.com/threads/backup-restore-error.56917/post-262174](https://forum.proxmox.com/threads/backup-restore-error.56917/post-262174)

We need improved validation job to ensure backups are successful or fail the backup if a basic decompression yields " restore failed - short vma extent". Just like writing a SD Card or burning a CD, their should be a step to ensure the resulting backup file matches its checksum.

Ran into this problem today - I have a server with bad ram that has been backing up multiple backups.

Their a work around script I can run to ensure ALL my backups can decompress?

Attached the output

- [*<svg xmlns="http://www.w3.org/2000/svg" role="img"><title>task-hpz440-qmrestore-2024-03-31T17_17_18Z.log</title><use href="/data/local/icons/regular.svg?v=1734431476#file-alt"></use></svg>*](https://forum.proxmox.com/attachments/task-hpz440-qmrestore-2024-03-31t17_17_18z-log.65603/)

task-hpz440-qmrestore-2024-03-31T17\_17\_18Z.log

7.7 KB · Views: 5
- [*<svg xmlns="http://www.w3.org/2000/svg" role="img"><title>proxmox_package_versions.txt</title><use href="/data/local/icons/regular.svg?v=1734431476#file-alt"></use></svg>*](https://forum.proxmox.com/attachments/proxmox_package_versions-txt.65604/)

proxmox\_package\_versions.txt

1.5 KB · Views: 4

Last edited: Mar 31, 2024

- - [#19](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-649045)

> Their a work around script I can run to ensure ALL my backups can decompress?

Just do a decompression to /dev/null, which reads the file and ensures that you can decompress it (this applies to zstd compressed files):

Code:

```
root@proxmox /var/lib/vz/dump > zstd -d -o /dev/null vzdump-qemu-102-2023_05_19-07_52_47.vma.zst
vzdump-qemu-102-2023_05_19-07_52_47.vma.zst: 2602409472 bytes
```

or even better

Code:

```
root@proxmox /var/lib/vz/dump > zstd --no-progress -d --no-sparse -o /dev/stdout vzdump-qemu-102-2023_05_19-07_52_47.vma.zst | vma verify -v /dev/stdin
CFG: size: 701 name: qemu-server.conf
DEV: dev_id=1 size: 8589934592 devname: drive-scsi0
CTIME: Fri May 19 07:52:48 2023
progress 1% (read 85917696 bytes, duration 0 sec)
progress 2% (read 171835392 bytes, duration 1 sec)

[...]

progress 97% (read 8332247040 bytes, duration 10 sec)
progress 98% (read 8418164736 bytes, duration 10 sec)
vzdump-qemu-102-2023_05_19-07_52_47.vma.zst: 2602409472 bytes
progress 99% (read 8504082432 bytes, duration 10 sec)
progress 100% (read 8589934592 bytes, duration 10 sec)
total bytes read 8589934592, sparse bytes 5988696064 (69.7%)
space reduction due to 4K zero blocks 6.57%
```

Now you would know that the archive can be restored.

- - [#20](https://forum.proxmox.com/threads/restore-backup-failure-zstd-decompression.74636/post-649048)

> We need improved validation job to ensure backups are successful or fail the backup if a basic decompression yields " restore failed - short vma extent". Just like writing a SD Card or burning a CD, their should be a step to ensure the resulting backup file matches its checksum.
> 
> Ran into this problem today - I have a server with bad ram that has been backing up multiple backups.
> 
> Their a work around script I can run to ensure ALL my backups can decompress?
> 
> Attached the output

root@hpz440:/mnt/pve/nas.hivetechnologies.net/dump# **unzstd --test** vzdump-qemu-110-2024\_03\_20-22\_03\_32.vma.zst  
\_20-22\_03\_32.vma.zst : 20.3 GiB... \_20-22\_03\_32.vma.zst : Decoding error (36) : Restored data doesn't match checksum  
root@hpz440:/mnt/pve/nas.hivetechnologies.net/dump#

Going to write a Jenkins job to run "unzstd --test" on all my \*.vma.zst backup files.
