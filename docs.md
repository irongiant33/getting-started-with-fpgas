Assumes everything uses Nandland Go board. iCEcube2 release 202.12.27943, Lattice Diamond Programmer Version (64-bit) 3.13.0.56.2

## Environment Setup

1. download icecube2: [https://www.latticesemi.com/en/Products/DesignSoftwareAndIP/FPGAandLDS/iCEcube2#_4351BE10BA504435B5226390CF5D7D4C](https://www.latticesemi.com/en/Products/DesignSoftwareAndIP/FPGAandLDS/iCEcube2#_4351BE10BA504435B5226390CF5D7D4C)
2. download "FlexNet Utility License Files for Windows v11.16: [https://www.latticesemi.com/LatticeDiamond](https://www.latticesemi.com/LatticeDiamond)
3. download programmer standalone for Windows: [https://www.latticesemi.com/LatticeDiamond](https://www.latticesemi.com/LatticeDiamond)
3. contact Lattice to request floating license for hobbyist use: lic_admn@latticesemi.com <lic_admn@latticesemi.com>
4. when you receive an email back from Lattice, follow the instructions. It should have you request a new license via their subscription licensing page: [https://lattice.agiloft.com/ui/system/continue_flow.do;page=qW1tb3zM8jW4KWdLkrQsjLF3Z0g10009.al;en;CSRF_NONCE=5FFE41DCC9784937864CD3185F43C993?screenWidth=2552&clientOSTimeZone=America%2FNew_York](https://lattice.agiloft.com/ui/system/continue_flow.do;page=qW1tb3zM8jW4KWdLkrQsjLF3Z0g10009.al;en;CSRF_NONCE=5FFE41DCC9784937864CD3185F43C993?screenWidth=2552&clientOSTimeZone=America%2FNew_York)
5. you should receive another email with your `license.dat` file.
6. place the `license.dat` in the same folder as the FlexNet Utility Files from step 2.
7. edit `license.dat` according to instructions in [this video](https://www.youtube.com/watch?v=g5kkZ32GLo4). You should just have to edit your server hostname, the path to `mgcld.exe`, and the path to `lattice.exe`.
8. In windows, as administrator, set your environment variable for `LM_LICENSE_FILE` to `port@hostname`. This command will differ for Linux: `setx /m LM_LICENSE_FILE "7788@samsPC" `.
9. start your server: lmgrd -l C:\Users\samue\Documents\icecube2\license.txt -c C:\Users\samue\Documents\icecube2\license_55135.dat  
10. verify server is started: `lmutil lmstat -a -c 7788@samsPC `
11. launch icecube2. You should be G2G!

- to stop the server, `lmutil lmdown -c C:\Users\samue\Documents\icecube2\license_55135.dat`
- as another client, you will have to have your LM_LICENSE_FILE environment variable set in order to point to the license server. Depending on how many seats you have will determine how many clients can simultaneously access the resource; for example, for one seat, only one device can have the license checked out at a time.

- had to exit and reopen icecube for the pcf to appear under constraints file in the P&R flow

- in diamond programmer if one cable detection point doesn't work, try the other one. I had success with location 001 (COM27, the second COM port that came up) 