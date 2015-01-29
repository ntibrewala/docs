# BM-09 EVB & WICED SDK Reference Guide

### Downloads:
* 3.1.2 for Windows [here](https://www.dropbox.com/s/j4oqhyq2p8ivw2n/WICED-SDK-3.1.2-IDE-Installer.exe?dl=0)
* 3.1.2 for Mac [here]( http://community.broadcom.com/community/wiced-wifi/wiced-wifi-documentation)

### Additional Files in Repository
* **BCM9WCDUSI09.zip** - BM-09 Platform support files for SDK version 3.1.2

### WICED SDK Installation
1. Install the IDE and take note of default project directory
  - Default directory for windows is under `%My Documents%\WICED\WICED-SDK-3.1.2\WICED-SDK`
2. Extract the contents of *BCM9WCDUSI09.zip* into the `platforms` folder in the project directory
  - Default directory for windows is under `%My Documents%\WICED\WICED-SDK-3.1.2\WICED-SDK\platforms`

  ![Extract Folder](/SenSing/Wiced SDK & BM-09 Reference/Screenshots/folder_copy.png)

3. Copy the existing Make Target `snip.scan-BCM943362WCD4` and paste it

  ![Copy Make](/SenSing/Wiced SDK & BM-09 Reference/Screenshots/copy_make.png)

4. Rename the new Make Target to `snip.scan-BCM9WCDUSI09`

  ![Rename Make](/SenSing/Wiced SDK & BM-09 Reference/Screenshots/paste_make.png)

5. Repeat steps 3 and 4 and create 2 more Make Targets:
  * `snip.scan-BCM9WCDUSI09 download`
  * `snip.scan-BCM9WCDUSI09 download run`
  ![Mutliple Make](/SenSing/Wiced SDK & BM-09 Reference/Screenshots/multiple_make.png)

Executing `snip.scan-BCM9WCDUSI09 download run` while the EVB is connected and drivers are properly installed, should compile, download and run the binary file for the scan snip.

### Additional Information
* Drivers for the EVB are under `%My Documents%\WICED\WICED-SDK-3.1.2\WICED-SDK\tools\drivers`
* Default baud rate for serial port: `115200`
* Useful links:
  * http://community.broadcom.com/message/7619
