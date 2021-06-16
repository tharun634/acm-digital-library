# Development Boards
## Arduino
This is the beginner's introduction to Embedded Systems. With its easy to learn ecosystem and the great many libraries and peripheral material available for virtually every imaginable use case, Arduino has become a staple for hobby embedded system designers.
 - The [official site](https://www.arduino.cc/) will provide the IDE, official documentation and a developer community forum to help get you started. It is recommended that you start with Arduino Uno as this is the most common entry level board with lots of documentation and community support.
 - [Top-Tech Boy's Arduino tutorials](https://toptechboy.com/arduino-lessons/) is a really good place to start learning Arduino. The content is comprehensive, and well structured, making it an invaluable resource to many people who are starting their journey with Arduino.
 - Programming using Embedded C saves up space and gets executed very fast. AVR C is the Embedded C used for AVR microcontrollers. This is the next step in your embedded programming. Learn this [here](https://www.youtube.com/playlist?list=PLA6BB228B08B03EDD).
## NodeMCU
This is the cheapest and most popular way to enter into the world of IoT for students. NodeMCU boards come WiFi enabled so you can connect your embedded solutions to the world, in short, this is your Welcome to IoT. There are two most common variants of NodeMCU:
- NodeMCU ESP8266:This is the older version, it is the easiest to start with and can introduce you to iot.
- A lot of web resources provide tutorials on how to get started with this, one such resource is given [here](https://www.electronicshub.org/getting-started-with-nodemcu/).
-If you want to explore more on what you can do with this little wonder, you can look at this list of [project tutorials](https://randomnerdtutorials.com/projects-esp8266/). *Tip: A lot of these projects use Raspberry Pi as a host, if you don't want to use it, you can replace it with your laptop*.
- NodeMCU ESP32: This is the more advanced development board. ESP32 comes with two cpu cores in instead of one, so you can multitask. It also comes with Bluetooth facility in addition to the standard WiFi.
- You can start with NodeMCU using Arduino IDE [here](https://randomnerdtutorials.com/installing-the-esp32-board-in-arduino-ide-windows-instructions/),
- Further projects can be seen [here](https://randomnerdtutorials.com/projects-esp32/).
## Raspberry Pi
This is for those who want serious computing power in their embedded applications. This is mostly used for computer vision, and deep learning applications.
- The [official site](https://www.raspberrypi.org/) will help you get started with the software and provide documentation on your development board.
- Recommended usage is headless(without a monitor). For this install the raspbian os with ssh, WiFi and vnc enabled, tutorial lik is provided [here](https://www.youtube.com/watch?v=ntaXWS8Lk34).
  - You may use either [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/) for a vnc connection (vnc connection is like connecting to a remote desktop), tutorial is provided [here](https://www.raspberrypi.org/documentation/remote-access/vnc/). You may use [Fing app](https://play.google.com/store/apps/details?id=com.overlook.android.fing&hl=en_IN&gl=US) to find out your Raspberry Pi's network address.
  - You may also connect using SSH connection, you will get only command line connection, but it takes less resources of your Rpi. Try [MobaXTerm](https://mobaxterm.mobatek.net/) or [Putty](https://www.putty.org/). MobaXTerm is preferred as it comes with additional features like its own IDE, provision for viewing cpu, ram and rom usage, etc.
- [TopTech Boy's tutorials](https://toptechboy.com/raspberry-pi-with-linux-lessons/) will help you cover the basics of Raspberry Pi.
