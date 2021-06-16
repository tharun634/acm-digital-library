# IoT Resources

## IDE
- [Arduino IDE](https://www.arduino.cc/en/software) is used for all Arduino devices to code them in both Arduino C and AVR C. Additionally, it can be used to program ESP devices too (ESP32, ESP8266).
- [Eclipse IDE](https://www.eclipse.org/ide/) is used in a lot of Embedded C development due to its support for ARM/RISC 5 support.

## Simulators
- [TinkerCAD](https://www.tinkercad.com/) can be used to simulate basic Arduino systems.
- [Proteus](https://www.labcenter.com/) can be used to design more complex systems on Arduino and using different peripherals.
-[Simulink](https://in.mathworks.com/products/simulink.html) is not just a simulator, they can be used to program your code in SIMULINK models. Easy prototyping can be done using block diagrams and Simulink generates optimized code for the target platform. Designing can be done for a lot of development boards, a few are [Arduino](https://in.mathworks.com/hardware-support/arduino-simulink.html) and [Rasberry Pi](https://in.mathworks.com/hardware-support/raspberry-pi-simulink.html)

## IoT Platforms
- [Thingspeak](https://thingspeak.com/) is a an IoT platform provided by Mathworks. Apart from collecting data from devices, one can also employ MATLAB analysis to compute on the data.
- [Firebase](https://firebase.googlehttps://www.labcenter.com/.com/?gclid=CjwKCAjw2ZaGBhBoEiwA8pfP_shoIb6thrmSm5rrEX51tshSQn7CLqO3-x1mFj2qqcFWhFbEL_345hoCypMQAvD_BwE&gclsrc=aw.ds), provided by Google, is a cloud service. Using this one can build real time databases that can help in building iot networks. Firebase makes compatibility of devices with apps extremely easy.
- [Blynk](https://blynk.io/) is an iot platform that incorporates simplicity and is also focused on developers.
- [Ubidots](https://ubidots.com/) is an iot platform that simplifies most aspects of iot analytics. It is more of a service oriented platform than a developer oriented one.

## Embedded OS
- [FreeRTOS](https://www.freertos.org/) is a [real time](https://www.geeksforgeeks.org/real-time-operating-system-rtos/) lightweight operating system that is used for embedded systems. It can be used if one wants to run processes concurrently and time is of essence. ESP32 uses FreeRTOS, getting started with it is given [here](https://icircuit.net/esp32-introduction-freertos/1297) and programming freertos using Arduino IDE is provided [here](https://exploreembedded.com/wiki/Setting_Up_FreeRTOS_on_Arduino).

-[Raspberry Pi OS](https://www.raspberrypi.org/documentation/raspbian/) is a linux based os used in Raspberry Pi boards.

## Miscellaneous
- [Mosquitto](https://mosquitto.org/) is an open source MQTT Broker, useful for lightweight data transport.
