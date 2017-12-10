## Concept

Do you like bright shiny lights? Have you ever wished you could have bright
shiny lights controlled by your smartphone? That is what this project was
about. Clara wanted to add some mood lighting to decorate her bedroom and we
figured it would be cool if she could change the lights to go with the desired
mood.

  

{% include youtube.html id="Jb4Bkz_O9vs" %}

  

## Design

  

We are using an [Arduino compatible](https://www.arduino.cc/) microcontroller with a bluetooth module. This allows us to drive LED-programmable lights (Neopixels) with a widely available library, and from the Arduino environment we have some experience in, while enjoying all the coolness of controlling from a smartphone app.

  

The folks at Adafruit made this project a lot easier and so we use their
hardware primarily. It would probably be cheaper to use a Wemo-type device
with Wifi. The ESP32 supports both Wifi and bluetooth and can be programmed in
MicroPython instead of Arduino.

  

5v power comes into a barrel jack and is fed through a capacitor to smooth it
out, to the Neopixel strip, to the Arduino, and to a logic level converter.
Out of PIN 6 comes the signal that drives the Neopixels because this Arduino
has 3.3v logic levels and Neopixels expect 5v logic levels.

  

  

## Parts

[Feather 32u4 Bluefruit LE](http://amzn.to/2kN0rSn)

[TXB108 Level shifter or similar](http://amzn.to/2BQcQIy)

[4700uF capacitor (a smaller one would also work)](http://amzn.to/2iIDxHz)

[2.1mm barrel jack](http://amzn.to/2kMXfWI)

[300 ohm resistor (or thereabouts)](http://amzn.to/2AQJvAg)

[Permaprotoboard](http://amzn.to/2iMlG2D)

[Neopixel strip(s)](http://amzn.to/2kN3l9J)

[5v power supply (I use a 10A one)](http://amzn.to/2Ab2imE)
  

## Layout
![fritzing]({{"/assets/neopixel_bluetooth_bb.png"}})  

[Fritzing File]({{"/assets/neopixel_bluetooth.fzz"}})

## Physical buildout

  

![front of the pcb]({{"/assets/img_20171126_235901.474.jpg"}})

  

![back of the pcb]({{"/assets/img_20171126_235915.149.jpg"}})

  

  

## References

  

  * About Bluetooth LE - <https://learn.adafruit.com/introduction-to-bluetooth-low-energy/gatt?view=all>
  * Adafruit Feather 32u4 Bluefruit - <https://learn.adafruit.com/adafruit-feather-32u4-bluefruit-le/pinouts?view=all>
  * Neopixel Überguide -<https://learn.adafruit.com/adafruit-neopixel-uberguide/downloads?view=all>
  * Shifting 3.3v to 5v - <https://learn.adafruit.com/neopixel-levelshifter/shifting-levels>
  * Bluefruit LE Android / iOS control app - <https://learn.adafruit.com/bluefruit-le-connect-for-ios/controller>
  * Source code of the app - <https://github.com/adafruit/Bluefruit_LE_Connect_Android>
  * Format of the data that is sent from the app - <https://learn.adafruit.com/bluefruit-le-connect-for-ios/controller>
  * Other similar projects - <https://learn.adafruit.com/bluetooth-controlled-neopixel-headphones/assembly?view=all>


## Software

[Arduino Sketch](https://github.com/samaparicio/neopixel_bluetooth)


## Control


Open the Bluefruit LE app ([Android](https://play.google.com/store/apps/details?id=com.adafruit.bluefruit.le.connect&hl=en) or [iOS](https://itunes.apple.com/us/app/adafruit-bluefruit-le-connect/id830125974?mt=8_)), select your bluefruit and connect. Then go into
Control.

You can then pick a color with the color picker or use the Control Pad to play
the following effects.


![how to control the lights]({{"/assets/screenshot_20171209-120825.jpg"}})
  

UP Arrow - **All One Color** , you can change the color with the ColorPicker

DOWN Arrow - **Fire**

LEFT Arrow - **Color Wipe** , you can change the color with the ColorPicker

RIGHT Arrow - Twinkle Random

  

1 **TheatreChaseRainbow** (takes long time to change back)

2 **ChooChoo** Train (Cylon eye - takes long time to change back)

3 **RGB Loop** (takes long time to change back)

4 **RainbowCycle** (takes long time to change back)



## Lessons learned while building

  * Using a cheap protoboard without +/- rails complicates things unnecessarily
  * Check the resistors with a meter before installing, they may not be of the value you think
  * You cannot reasonably expect a micro controller with one voltage level for logic (3.3) to control a sensor or device with logic at another level (5v)
  * When soldering, check for continuity with a meter, will save you time later
  
## Shoutouts
 * Shane Smith at Nova Labs for helping us figure out we were using the wrong resistors
 * Becky Stern at Adafruit for writing a [sketch with the bluetooth code](https://learn.adafruit.com/adafruit-feather-32u4-bluefruit-le/controller)
 * Shout out to [Adafruit](http://adafruit.com) for making awesome hardware
 * Shout out to Tweaking4All for [writing the pixel animations](https://www.tweaking4all.com/hardware/arduino/adruino-led-strip-effects/)

