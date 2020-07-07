Thu Mar  6 17:19:00 CST 2014
SecuGen FDx SDK PRO for Unix/Linux
Version 3.7.1 
#################################################################

At revision 570.
================================================================ 
Release Notes:
================================================================= 
1. This version supports the following SecuGen devices:
    USB Hamster PRO 20 VID:0x1162 PID:0x2200 (U20 class device)
    USB Hamster IV VID:0x1162 PID:0x330 (FDU04 class device)
    USB Hamster IV VID:0x1162 PID:0x2000 (SDU04P class device)
    USB Hamster Plus VID:0x1162 PID:0x320 (FDU03 class device)
    USB Hamster Plus VID:0x1162 PID:0x322 (SDU03M class device)
2. This version supports (has been tested with) the following Linux versions:
    ARM Linux 2.6.29 #1123 Tue Dec 27 21:43:44 CST 2011 armv5tej1 GNU/Linux
    libusb-0.1-4 (2:0.1.13)
    gcc version 4.2.0 20070413 (prerelease) (CodeSourcery 2007q1-10. Marvell 2008q3-13 20081204)


================================================================= 
SYSTEM INSTALLATION NOTES
================================================================= 
1. Unzip the distribution 

2. Plug in the Hamster Plus or Hamster IV device

3. export LD_LIBRARY_PATH=../../lib/arm12

4. cd <installdir>/bin/arm12

5. Now you are ready to run the demo programs in the 
    <installdir>/bin/arm12 directory

6. Binaries linked with Hamster Plus driver are appended with "_fdu03"

7. Binaries linked with Hamster IV driver are appended with "_fdu04"


================================================================= 
Java development
================================================================= 
JDK version 1.6.0_24 or later is required for distributions supporting Java

================================================================= 
Bug Fixes/Enhancements
================================================================= 
v3.7.0 REV477 2014-1-2  Hamster PRO 20 is now supported
v3.5.6 REV329 2013-2-25 Java now supported
v3.5.5 REV311 2013-2-13 Multiple devices of same class now supported.
                        FDU04 and FDU03 class devices cannot be used
                        concurrently within the same application. Multiple
                        FDU04 class devices can be used concurrently. 
                        Multiple FDU03 class devices can be used concurrently.
                        Fixed null S/N returned for SDU03M and SDU03P
v3.5.4 REV232 2012-09-28 Fixed auto on sample code
v3.5.4 REV219 2012-09-28 Added support for 512KB SDU04P
                        Fixed problem with exposure settings. Image quality is 
                        improved
v3.5.3 RC1    2012-06-25 Add support for SDU04P, FDU03 and SDU03P
v3.5.3 Beta1  2009-12-10 Initial Release


================================================================= 
Building the demo programs
================================================================= 
-----------------------------------------------------------------
FPLIB TEST SAMPLE
    cd <installdir>/sgfplibtest
    make
    ../bin/arm12/sgfplibtest_fdu04 to run the program
-----------------------------------------------------------------
AUTO_ON TEST SAMPLE
    cd <installdir>/auto_on
    make
    ../bin/arm12/auto_on_fdu04 to run the program
-----------------------------------------------------------------

