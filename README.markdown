The Pololu Serial Servo API for Arduino
=======================================

This is an Arduino library for using the [Pololu Serial Servo controller](http://www.pololu.com/catalog/product/207 Part #207) in Pololu mode (jumper is not shorting).

Written by Christopher Wojno in May 2012.
https://github.com/wojnosystems/pololu-ms8sc-pololu-mode

Installation
------------

To use this [library](http://arduino.cc/en/Hacking/LibraryTutorial), you must first install it. This will depend entirely on where your Arduino project files are stored.

The Arduino project files are stored on a Mac in:

* ~/Documents/Arduino

Where ~ is your home directory.

Under the Arduino project files directory, you need a folder called "libraries" which may or may not exist. Create it if it does not exist. Finally, copy all of the files from the project into a folder inside of libraries called "CwPololuSerialServo."

If you have git and a command line, here is a script to automagically install the library for you:

install.bash:

	mkdir ~/Documents/Arduino/libraries
	git clone git://github.com/wojnosystems/pololu-ms8sc-pololu-mode.git ~/Documents/Arduino/libraries/CwPololuSerialServo

Remember, relaunch the Arduino IDE before trying to use any newly imported libraries.

Testing
-------

Yup. I wrote a testing library for this as well for my sanity. Not everything is implemented, but of what has been implemented, it's all been tested and confirmed to behave as expected.

To test this library, you can use the included test suite: CwPololuSerialServoTest.ino. You'll also need a working [Arduino Mega](http://arduino.cc/en/Main/ArduinoBoardMega2560) or something with at least 3 serial ports as one talks with the host PC to report test results, 1 is the output of the serial commands generated by this library, and the last serial port reads the commands generated by the second serial port. Thus, you'll need to bridge the RX port of Serial 3 (RX2 AKA port 17) with TX port of Serial 2 (TX1 AKA port 18).

Common errors
-------------

If your serial controller's read LED is flashing after you try to talk with it, then your BAUD rate may be set too hight. Try the recommended value in the docs: 45,000 and lower it if it's still giving you trouble.

Warrantee
---------

This library and all it's files are provided as-is. Author is not responsible for it's misuse or any injury or damage caused by its use. Use at your own peril and discretion.
