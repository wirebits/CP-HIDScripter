# 🐍CP-HIDScripter

# ℹ️About
CP-HIDScripter (CircuitPython-HIDScripter) is a web tool that generates circuitpython HID scripts using Mnemonics.

# ⏳Working
It basically converts the mnemonics with values into circuitpython scripts so that it directly store on flash memory to perform keystroke injection.

# ✨Features
- Simple and clean GUI.
- Two large windows one for mnemonics and other for circuitpython script.
- Convert Button : Convert mnemonics into circuit python scripts.
- Copy Button : Copy circuitpython script to the clipboard so that it can paste anywhere.
- Reset Button : Clear all text from both windows.
- Save Button : Save circuitpython scripts on the system for future use.
- From Button : Upload `.txt` files which contain mnemonics to load on mnemonics window.

# 🎥Demo Video
https://github.com/user-attachments/assets/cecb20a6-ce4c-40ff-9895-c819e930ed7d

# ✅Supported Boards
- Those boards which support `CircuitPython` and it supports `usb_hid` module.

>[!TIP]
> Use those boards which have atleast `2MB` flash memory.

>[!CAUTION]
> - Some boards does not have built-in UF2 bootloader.  
> - It need to flash UF2 bootloader to allows you to flash your firmware by just dragging and dropping `.uf2` file onto the flash drive without using an external programmer.  
> - Check CircuitPython page of that board.  
> - At the end of the page, if it contain link for bootloader `.bin` file, that means it does not have built-in UF2 bootloader.

# 📦Requirements
- `1` Your Board
- `1` Micro-B USB / Type-C USB Cable with data transfer support

# ⚙️Setup CircuitPython
1. Open Official CircuitPython download link from [here](https://circuitpython.org/downloads).
2. Search your board you have.
3. Select your board and click on it.
4. Download latest stable release CircuitPython `.uf2` file and noted its version.
   - It is like `X.Y.Z`.
   - Latest stable release is `9.2.9` but it can be changed in future so keep eye on it.
5. Connect your board with Micro-B USB / Type-C USB Cable and then connect it to the PC/Laptop.
   - It is shown as Mass Storage Device with some name.
6. Copy the `.uf2` file into the board mass storage device.
   - When it is copied, then it disconnects automatically and reconnect as `CIRCUITPY`.
7. Done! CircuitPython is successfully flashed in the your board.

# ⚙️Setup Essential Files
1. Make sure that your board is connected to your PC/Laptop.
2. Download latest Adafruit CircuitPython Bundle from [here](https://circuitpython.org/libraries).
   - There are `2` variants of libraries : `Bundles` and `The Community Bundle`.
   - In Bundles variant, download latest stable Adafruit CircuitPython Bundle as noted version of `.uf2` file.
   - Latest stable release is `adafruit-circuitpython-bundle-9.x-mpy-20250829.zip` but it can be changed in future so keep eye on it.
3. Extarct the ZIP file.
4. Go to the `lib` folder in the extracted ZIP file.
5. Copy `adafruit_hid` folders in the `lib` folder of `CIRCUITPY`.
6. Done! Now, your board is ready to use as a DIY USB Rubber Ducky.

# 💡Mnemonic Table
| Mnemonic |                                                                                          Description                                                                                          | Example                             |
|:--------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|-------------------------------------|
| CMT      | It used to add comments in the code.                                                                                                                                                          | CMT This is a test script           |
| TIME     | It adds the time library in the code.                                                                                                                                                         | TIME                                |
| HID      | It adds the usb_hid library in the code.                                                                                                                                                      | HID                                 |
| HWD      | It adds the board and digitalio libraries in the code.                                                                                                                                        | HWD                                 |
| KEYBOARD | It adds the Keycode, Keyboard and KeyboardLayoutUS libraries and also create objects for keycode and keyboard layout in the code.                                                             | KEYBOARD                            |
| MOUSE    | It adds the Mouse library and also create objects for mouse in the code.                                                                                                                      | MOUSE                               |
| PIN      | It add pin declaration in the code.                                                                                                                                                           | PIN                                 |
| LED      | It turns on/off the led in the code.<br>Values are ON and OFF.                                                                                                                                | LED ON                              |
| WAIT     | It add time in the code.<br>Time is in milliseconds.<br>1000 ms = 1 second.                                                                                                                   | WAIT 1000                           |
| TYPE     | It add text want to type in the code.                                                                                                                                                         | TYPE Hello World!                   |
| MOVE     | It moves the mouse pointer according to the values.<br>Values are x-axis, y-axis and scroll.<br>Values may be positive, negative or ZERO.<br>Values in sequence - x-axis -> y-axis -> scroll. | MOVE 36 -78 0                       |
| CLICK    | It clicks the mouse buttons.<br>Values are LEFT, MIDDLE and RIGHT.                                                                                                                            | CLICK LEFT                          |
| PRESS    | It press the mouse buttons and releases immediately.<br>Values are LEFT, MIDDLE and RIGHT.                                                                                                    | PRESS RIGHT                         |
| LOOP     | It run commands for a certain number of times.                                                                                                                                                | LOOP 3<br>TYPE Hello World!<br>EXIT |
| INF      | It run commands infinitely.                                                                                                                                                                   | INF<br>TYPE Hello World!<br>EXIT    |
| EXIT     | It used to close both LOOP and INF blocks.                                                                                                                                                    | EXIT                                |
# 🔡Supported Symbols
`~`
- is used to add `\n` at the end of the text.
- It is used when TYPE mnemonic in working.
- `TYPE Hello~` gives the output `layout.write("Hello\n")`.

# 📝Supported Mnemonics
## Alphabet Keys
`A` `B` `C` `D` `E` `F` `G` `H` `I` `J` `K` `L` `M` `N` `O` 
`P` `Q` `R` `S` `T` `U` `V` `W` `X` `Y` `Z`
## Function Keys
`F1` `F2` `F3` `F4` `F5` `F6` `F7` `F8` `F9` `F10` `F11` `F12`
## Navigation Keys
`LEFT` `UP` `RIGHT` `DOWN` `TAB` `HOME` `END` `PGUP` `PGDN`
## Lock Keys
`CAPS` `NUM` `SCROLL`
## System and GUI Keys
`GUI` `ESC` `PRTSCR` `PAUSE`
## Editing Keys
`INSERT` `DEL` `BKSP` `ENTER`
## Modifier Keys
`CTRL` `SHIFT` `ALT`

# 🏃🏻‍♂️Run `DIY USB Rubber Ducky`
1. Make sure that your board is connected to your PC/Laptop and it has essential files.
2. Open CP-HIDScripter from [here]().
3. Type mnemonics in mnemonics window.
4. Click on `Convert` button.
   - The corresponding CircuitPython script is generated.
5. Click on `Save` button.
   - It generates a file named `code.py`.
   - It is default file in `CIRCUITPY` so that when powered the board, this file is running.
   - It ask for replacement of `code.py` file, then replace it.
   - It will overwrite in the `code.py` file.
6. Done! As `code.py` saved in it, the script executes automatically.

>[!TIP]
> Start your code with `WAIT` so that board get time to initiate.
>Time must be atleast `1000`.

# 📖Examples
- Just copy the example and paste in mnemonics window and click on `Convert` button.

## 1. Blink LED
```
CMT Blink LED Exploit

TIME
HWD

PIN

INF
LED ON
WAIT 1000
LED OFF
WAIT 1000
EXIT
```

## 2. Open Notepad and Type
```
CMT Type on notepad Exploit

TIME
HID
KEYBOARD

WAIT 1000
GUI R
WAIT 1000
TYPE notepad
WAIT 1000
ENTER
WAIT 1000
TYPE This is a test script developed by CP-HIDScripter!
```

## 3. Open CMD as Administartor Mode
```
CMT Open CMD as Administrator Exploit

TIME
HID
KEYBOARD

WAIT 1000
GUI R
WAIT 1000
TYPE cmd
WAIT 1000
CTRL SHIFT ENTER
WAIT 1200
ALT Y
```

## 4. Create a folder
```
CMT Folder Creation Exploit

TIME
HID
KEYBOARD

CTRL SHIFT N
WAIT 1100
TYPE Test
WAIT 1200
ENTER
```

## 4. Open Notepad and Type 5 Times
```
CMT Type on notepad 5 times Exploit

TIME
HID
KEYBOARD

WAIT 1000
GUI R
WAIT 1000
TYPE notepad
WAIT 1000
ENTER
WAIT 1000

LOOP 5
TYPE This is a test script developed by CP-HIDScripter!~
EXIT
```

## 5. Mouse Jiggler
```
CMT Mouse Jiggler Exploit

TIME
HID
MOUSE

INF
MOVE 2 0 0
WAIT 500
MOVE -2 0 0
WAIT 500
EXIT
```
