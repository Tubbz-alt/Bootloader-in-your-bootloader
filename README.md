# Bootloader-in-your-bootloader
bootloader in your bootloader
The only thing you need to add is a VCRHYB64 download file (apparently to large), just type "VCRHYB64" into google and add in to these files.
Put all these files on a stick and away you go, installs windows 7 and dual operation at same time of windows 10 & 7
Or direct straight install on windows 7 using windows 10  update files to update windows 7

Some of the features I implemented in the last version of wufuc have turned out to not be as useful as I thought, or caused more problems than they were worth (crash detection, API hooking, etc). So I brought wufuc back to basics with this version.

Changes in this release
Removed crash-detection. (fixes #148)
Removed all injection and API hooking routines. (fixes #146 and hopefully #147)
Patching routines are now fully external:
Way more stable and less invasive, crashes and hangs should be pretty much non-existent.
Re-introduces the incompatibility with UpdatePack7R2 or other software that modify wuauserv's ServiceDll value in the registry. You can still work around this manually by using the provided Restore_wuauserv.reg file.
Introduces a potential race condition where the "Unsupported hardware" popup could display for a short period of time before wufuc is able to patch it. Should this happen, just close the popup and it should not display again.
Changed the log file text encoding format from UTF-16LE (without BOM) to UTF-8 (without BOM) to improve compatibility with various text editors. Because of this, the log file is now located at C:\ProgramData\wufuc\wufuc.1.log.
