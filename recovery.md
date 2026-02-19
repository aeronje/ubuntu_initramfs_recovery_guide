# Recovery steps

> This issue occurs more frequently on systems using mechanical HDDs due to slower write speeds and moving parts.  
> SSDs are not exempted to sudden power loss but generally more resilient and recover faster.  
> Upgrading to an SSD is still recommended though.

**At the (initramfs) prompt, please run lsblk**

```lsblk```

**If lsblk does not show anything then try**

```blkid```

**Look for your Linux partition typically something like**

```/dev/sda5  TYPE="ext4"```

**Run Filesystem Repair**

```fsck -yf /dev/sda5```

***-f → Force check even if marked clean and -y → Auto-answer "yes" to repair prompts***

**Wait until you see something like this**

```***** FILE SYSTEM WAS MODIFIED *****```

***This means the repair completed, this is almost like CHKDSK in Windows***

**Run exit then reboot**

```exit```

```reboot -f```

***I used reboot -f instead***

# Desperate moves if it still Fails

**Check for**

> Wrong partition selected.

> Loose SATA/power connection.

> Repeated I/O errors (possible failing drive).

**If errors persist after multiple fsck attempts**

> Consider backing up data (if accessible).

> Replace HDD or sometimes check physical SATA connection. ***(NVRAM unseat/reseat)***

> Reinstall Ubuntu.
