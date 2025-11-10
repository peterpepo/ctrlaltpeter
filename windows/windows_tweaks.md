# Windows Tweaks

## Disable Fast Startup

   ### What is (not) the Fast Startup

   Disables Fast Startup, or so called "Hybrid Shutdown" - if you will. It is a feature to allow for faster startups by shutting down programs and "hibernating" the kernel with loaded drivers to the drive. It is defacto a mixture between hibernate and shut down.

   Among with others it:
   - Causes unnecessary writes to the SSD
   - Might cause other issues by not performing the full shutdown / fresh load every boot

   The easiest way to check and spot it is turned on is to:
   1. Open the Task Manager
   2. Performance
   3. CPU
   4. Up Time - You are going to have time much greater then the current session / windows "on time" - hours, sometimes even days.
   
   Please note, that this is a different to **Fast boot** option in bios, which usually skips some checks, boot options, ability to pick boot device or invoke BIOS(UEFI) options.

   ### To disable Fast Startup
   
   1. `WIN+R` (Run)
   2. `control` - opens classic (old school) Control Panel
   3. Power Options
   4. Choose what the power buttons do
   5. Change settings that are currently unavailable
   6. Turn On Fast Startup (Recommended)
   7. Uncheck
   ![Win11 - disable fast startup](./02_disable_fast_startup.png)
   8. Save changes
   9. Enjoy the fresh kernel each boot