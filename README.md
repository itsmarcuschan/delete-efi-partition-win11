# Delete an EFI Partition on Windows 11

⚠️ **Warning:** This operation will erase the EFI partition.  
If you perform this on your system disk (where Windows is installed), your PC will no longer boot.  
Only use this on a secondary disk or before a full reinstallation.

---

## Step 1 – Open Command Prompt as Administrator
1. Right-click on the **Start Menu**.  
2. Choose **Windows Terminal (Admin)** or **Command Prompt (Admin)**.  
3. Run the following command:

```cmd
diskpart
```

---

## Step 2 – Identify the target disk
1. List all disks:

```cmd
list disk
```

2. Identify the number of the disk you want to modify (⚠️ double-check, as everything will be erased).  
   Example output:

```
Disk ###  Status         Size     Free     Dyn  Gpt
--------  -------------  -------  -------  ---  ---
Disk 0    Online         512 GB   0 B
Disk 1    Online         256 GB   256 GB
```

---

## Step 3 – Select the disk

```cmd
select disk X
```

> Replace `X` with the number of the disk you want to clean.

---

## Step 4 – Delete the EFI partition
1. List all partitions:

```cmd
list partition
```

2. Select the EFI partition (usually ~100–300 MB, type *System*):

```cmd
select partition Y
```

3. Delete the partition:

```cmd
delete partition override
```

---

## Step 5 – (Optional) Wipe the entire disk
If you want to start from a completely clean disk:

```cmd
clean
```

---

✅ Your disk is now ready to be reused.
