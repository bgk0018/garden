---
{"dg-publish":true,"dg-path":"articles/2025-01-11 - Home Server Catastrophic Failure Review","permalink":"/articles/2025-01-11-home-server-catastrophic-failure-review/","title":"2025-01-11 - Home Server Catastrophic Failure Review","tags":["🥕"],"created":"2025-05-12T23:14:29.732-05:00","updated":"2025-01-11T22:10:46.990-06:00"}
---


# Home Server Catastrophic Failure Review

On [[archive/2024/journal/daily/2024-12-09\|2024-12-09]] after adding a new user into Authentik, I noticed that I was unable to access a service hosted in my `container-services` VM in Proxmox. I had noticed that I had been having some stability issues over the last month or 2, but after a restart it seemed to run typically pretty fine for a few weeks.

I generally wasn't too concerned about this, as in the past if I had an issue I was able to successfully restore from backup the VM and continue on

I hopped into the terminal and was greeted with what only could be described as a wall of gibberish text.

I assumed that I had somehow gotten into a bad state again and what I needed to do was just go ahead and delete and restore from backup.

Except the backup didn't restore. It would move through the decompression steps slowly, and eventually around 70% it bailed.

I ended up trying some backups from over a month earlier and those also failed similarly.

![Home Server Catastrophic Failure Review  - 202501111145-20250111174400243.webp](/img/user/blog/articles/2025-01-11%20-%20Home%20Server%20Catastrophic%20Failure%20Review/Home%20Server%20Catastrophic%20Failure%20Review%20%20-%20202501111145-20250111174400243.webp)

I also tried to go and look at the snapshots I had of the SMB share in which I'm currently storing the qcow2 file for the VM's hard disk, but it was empty.

So at this point I thought I was hosed. I went and did some reading on the error messages, and one [[blog/articles/2025-01-11 - Home Server Catastrophic Failure Review/Restore backup failure (zstd decompression)\|thread]] in the Proxmox forums pointed to bad memory. It made sense since I had been experiencing a lot of system instability.

The impact of this data loss is significant in terms of effort, but not in terms of irreparable damage. All documents, images, videos, etc. are all stored separately from the `container-services` and so the really important data was preserved. What would be lost, however, is hours of configuration, troubleshooting, and tweaking I've done over the last 1.5 years to get all my services into a shape I want them to be.

## What Happened?

The next weekend, I went ahead and pulled the server upstairs and plugged in a keyboard to go run MemTest64+ next to my main PC.

Immediately, Memtest detected issues. So I checked each stick of memory individually, both ended up having tons of errors.

I had originally upgraded the memory when I first got the computer and still had the old memory. When I popped those in and ran the memory test, everything came back fine.

So at this point I know I have a memory issue. As it turns out, TEAMGROUP has a lifetime warranty on their memory modules, so I submitted for that RMA immediately. If you have TEAMGROUP memory, you can check your warranty status [here](https://support.teamgroupinc.com/en/support/check_warranty.php). After dropping that off at the post office, I came back to begin again to see if I could restore from backup.

As it turned out, the most recent 2 weeks~ worth of backups were just bad. My guess is that because the memory was failing, it was not successfully creating the backups correctly. I ended up going back about 3 weeks and finally was able to find a backup that restored!

![Home Server Catastrophic Failure Review  - 202501111145-20250111174319653.webp](/img/user/blog/articles/2025-01-11%20-%20Home%20Server%20Catastrophic%20Failure%20Review/Home%20Server%20Catastrophic%20Failure%20Review%20%20-%20202501111145-20250111174319653.webp)

![Home Server Catastrophic Failure Review  - 202501111145-20250111174307833.webp](/img/user/blog/articles/2025-01-11%20-%20Home%20Server%20Catastrophic%20Failure%20Review/Home%20Server%20Catastrophic%20Failure%20Review%20%20-%20202501111145-20250111174307833.webp)

The other interesting thing that I couldn't have known is that at some point I moved the virtual hard disk away from the NAS SMB share, and instead had it directly on the server. This meant that my NAS snapshots of the dataset wouldn't have captured anything since we weren't saving to that location 🤦.

![Home Server Catastrophic Failure Review  - 202501111145-20250111175037551.webp](/img/user/blog/articles/2025-01-11%20-%20Home%20Server%20Catastrophic%20Failure%20Review/Home%20Server%20Catastrophic%20Failure%20Review%20%20-%20202501111145-20250111175037551.webp)

> *`homelab-services` snapshots weren't going to help anything if the disk wasn't being saved here!*

## What Did I Learn?

A few things, it might not be enough to just take backups. In fact, it looks like from the Proxmox documentation, I can actually set up [Verification jobs](https://pbs.proxmox.com/docs/maintenance.html#verification) that do exactly what would've mitigated this issue in the first place as I would've been notified when my backups were no longer being created in a valid state

Additionally, I need a more robust [notification](https://pbs.proxmox.com/docs/notifications.html#notifications) mechanism for this type of issue as well. I've been eyeballing [ntfy.sh](https://ntfy.sh/) for awhile, and it might be time to take the plunge there.

## What Questions Do I Have?

One of the things that I've heard about is ECC memory. The little Dell 5070 OptiPlex running my server from doesn't support ECC memory, but curious if it would've helped at all in this scenario.

At surface level, ECC memory is Error Correcting Code Memory, and basically can check for issues that occur in memory and increase stability.

Surely ECC memory can still go bad. I don't think it's likely a sufficient reason for me to ditch my current hardware anyway.

## References

[[blog/articles/2025-01-11 - Home Server Catastrophic Failure Review/Restore backup failure (zstd decompression)\|Restore backup failure (zstd decompression)]]
