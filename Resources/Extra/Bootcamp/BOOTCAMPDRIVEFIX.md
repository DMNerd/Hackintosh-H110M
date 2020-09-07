As I explained, Bootcamp was never meant to be run with multiple drives, so the setup just sets attributes of every other disk to Hidden.

How to fix it:
1. Open diskpart
2. Select the offending disk
3. Select its partition (Usually will have only one, otherwise repeat the next steps for all the partitions on the disk you want to get a letter)
4. Select the partition
5. Type  attributes volume and enter
6. You will see that Hidden has Yes after it - **that is what is causing it not to get a letter**
7. Type attributes volume clear hidden and enter
8. Jackpot - on reboot the drive should get its mount point

![Diskpart](https://raw.githubusercontent.com/DMNerd/Hackintosh/master/Resources/Screenshots/Diskpart.png)