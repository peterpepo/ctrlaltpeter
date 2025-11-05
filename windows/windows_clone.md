# Windows - Cloning

## Windows Slow Boot After SSD Clone

  After successfully cloning a working Windows 10 installation from a smaller 256 GB Intel NVMe SSD to a new Samsung 990 Evo NVMe SSD (using Clonezilla), the system began taking much longer to boot.
  
  The delay occurred after the BIOS check, during the Windows loading screen (with the spinning dots). Boot time increased from about 20 seconds to nearly 3 minutes.
  
  Once the system finishes booting, however, the SSD performs normally - there are no signs of slowness or lag. Benchmark results in CrystalDiskMark show expected read and write speeds, confirming that overall performance is unaffected. The issue only impacts the startup process.
  
  The cause was a mismatch between the old hiberfil.sys file and the new SSD’s ID (GUID).
  
  **Solution**:
  Disable hibernation to remove the existing hiberfil.sys file, then re-enable it to recreate the file correctly.

  After applying this fix, boot times immediately returned to normal - the system now starts up quickly again, within seconds.

### Disable + enable hiberfil.sys

  1. Open up a terminal `Win+R` -> `cmd` -> `ENTER`
  2. `powercfg /h off` - disables hibernation
  3. `shutdown /r /t 0` - restarts the computer
  4. System should already boot much faster now, if it does
  5. Open terminal again (step 1) and `powercfg /h on` - reenables hibernation

  