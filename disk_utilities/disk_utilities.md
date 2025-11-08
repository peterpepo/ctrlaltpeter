# Disk Utilities

## Wipe GUID (GPT) and MBR partition tables (Using GParted)

  Wipe all partition information - both GPT and MBR partition tables from a drive.

   1. Boot [GParted](../tools/tools.md#references)
   2. Find name of the device (using GParted GUI / lsblk from terminal), on partition table to be wiped, e.g. `/dev/nvme0n1`
   3. Open (double-click) **Terminal**
   4. Run gdisk on selected device `sudo gdisk /dev/<device>` - example `sudo gdisk /dev/nvme0n1`
   5. Enter following values to the prompt
   6. Command (? for help): `x`
   7. Expert command (? for help): `z`
   8. About to wipe out GPT on /dev/\<device\>. Proceed? (Y/N): `y`
   9. Blank out MBR (Y/N): `y`
  
## Check SMART information (Using GParted)

   Check SMART info using live-cd(usb).

   1. Boot [GParted](../tools/tools.md#references)
   2. Open (double-click) **Terminal**
   3. `sudo smartmonctl`

   