# Installing My GCCPCB 1.0 Code

The code I run on my GCCPCB's currently utilizes Nicohood's Nintendo library found here :

https://github.com/NicoHood/Nintendo

and MHeironimus' Arduino Joystick Library found here :

https://github.com/MHeironimus/ArduinoJoystickLibrary

and dmadison's Nintendo Extension Controller Library found here :

https://github.com/dmadison/NintendoExtensionCtrl

If this is the first time you have used these libraries, press Clone or download, and press Download ZIP on these repos. The Nintendo library and the Extension controller library are in the form they need to be in, but the joystick library is not.

![image](https://i.imgur.com/qxkgcJC.png)

Extract the Joystick folder out of the ArduinoJoystickLibrary-master ZIP file, and then ZIP the Joystick folder. You should have a Joystick.zip file, that contains the Joystick folder, that contains a src folder, an examples folder, and a file named library.properties.

Download GCCPCB-vX.Y.ino from the latest release here https://github.com/Crane1195/GCCPCB/releases. Make a folder with the same name as the file (GCCPCB-vX.Y) and put the .ino file in this folder. Place the newly created Joystick.zip file, as well as the Nintendo-master.zip file in this folder as well.

![image](https://i.imgur.com/W2LNSte.png)

Your folder should look like this.

Another thing you will need is the Arduino IDE, which is found here :

https://www.arduino.cc/en/Main/Software

![image](https://i.imgur.com/lZlK5E5.png)

After installing the Arduino IDE, open GCCPCB-XX.ino, and add the libraries using this menu option.

![image](https://i.imgur.com/RMcqLRM.png)

Navigate to where you have the GCCPCB-XX folder, and double click one, then repeat the process for the others. You will only need to install these libraries and the Arduino IDE once. For future updates, you will just have to download the new code, and upload it using the method below.

![image](https://i.imgur.com/Bc7xqCz.png)

In this menu, change the board to be Arduino/Genuino Micro.

![image](https://i.imgur.com/IPdVq6B.png)

Before plugging in the GCCPCB, look and see what Ports are there. On this machine, there were none, but on my other machine, I had a couple already.

![image](https://i.imgur.com/GjqfGvJ.png)

Plug in the board via USB, and check this menu again, you should see another COM port show up. For both of my computers, it will also say "Arduino/Genuino Micro", but it is possible it will not. What should always happen though, is a port should show up when you plug in the board, and should disappear when you unplug the board (make sure you close the menu and reopen it to refresh the list). This port is the port for the GCCPCB. Select it.

![image](https://i.imgur.com/u16W9HK.png)

If you are not using a Brook Board, you are ready to upload to the board. Click this button to do so.

![image](https://i.imgur.com/CY3OeIv.png)

This section of the IDE will say Compiling Sketch, then Uploading, then Done Uploading. When it says Done Uploading, the board is ready to use, and can be unplugged.

![image](https://i.imgur.com/8f7lK0G.png)

If you are using a Brook Board, and are not using the default layout shown here (Brook A corresponds to the B screw terminal on my board, etc), you will have to edit the pinout in the code.

![image](https://i.imgur.com/2Sreh0V.png)

This chart details which Arduino pin corresponds to which GCCPCB screw terminal which corresponds to what Brook Board input. Insert the button wires of the buttons you want to use for the Brook board into the terminal that matches the input.

![image](https://i.imgur.com/SL0nwQw.png)

Look for these lines. Their line numbers may not be the same, but it is near the top of the file. These values are the Arduino pins that correspond to the screw terminals on the board.

For an example: Lets say you want your Brook RB/LB to be in the traditional fighting game location, with an 8 button layout. What you would do, is plug your LB button into the screw terminal for A, and the RB button into the screw terminal for C-L. Then, you would plug your Gamecube controller A/C-L buttons into E1/E2 (Extra 1 and Extra 2). You would then change these numbers in the code.

```
const int A = XX      : XX would now be 11
const int CLEFT = XX  : XX would now be 10
const int EXTRA1 = XX : XX would now be 15
const int EXTRA2 = XX : XX would now be 9
```
If you have any problems with this, or need assistance setting up the button mapping, feel free to message me on Discord @Crane#1195 .

## Contact
If you have any questions or need any assistance in this process, feel free to message me on Discord @Crane#1195
