---
layout: post
title: "Bluetooth Neopixels"
date: 2017-12-09
---

## Concept

Do you like bright shiny lights? Have you ever wished you could have bright
shiny lights controlled by your smartphone? That is what this project was
about. Clara wanted to add some mood lighting to decorate her bedroom and we
figured it would be cool if she could change the lights to go with the desired
mood.

  

(video goes here)

  

## Design

  

We are using an Arduino micro controller with a bluetooth module. This allows
us to drive LED-programmable lights (Neopixels) with a widely available
library, and from the Arduino environment we have some experience in, while
enjoying all the coolness of controlling from a smartphone app.

  

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

![noteattachment1][3f6e0cbe56a62753036f40fa755b0776]
![noteattachment2][bcac705a1303034443e94a70dcb984af]

##Physical buildout

  

![noteattachment3][2306a2438e5d3dcffad47804b3909aaf]  

  

![noteattachment4][e43f2d8d317addb9458f1b98fcb76029]  

  

  

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

Link to Github goes here


## Control


Open the Bluefruit LE app, select your blue fruit and connect. Then go into
Control.

You can then pick a color with the color picker or use the Control Pad to play
the following effects.

  

  

  

![noteattachment5][1147de98693ebad9ceb25d5b868106a7]  

  

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

  


---
### ATTACHMENTS
[1147de98693ebad9ceb25d5b868106a7]: media/screenshot_20171209-120825.jpg
[screenshot_20171209-120825.jpg](media/screenshot_20171209-120825.jpg)
>hash: 1147de98693ebad9ceb25d5b868106a7  
>timestamp: 19700101T000000Z  
>application-data: image  
>reco-type: unknown  
>file-name: screenshot_20171209-120825.jpg  

[2306a2438e5d3dcffad47804b3909aaf]: media/img_20171126_235901.474.jpg
[img_20171126_235901.474.jpg](media/img_20171126_235901.474.jpg)
>hash: 2306a2438e5d3dcffad47804b3909aaf  
>timestamp: 20171127T075901Z  
>latitude: 38.9083  
>longitude: -77.3918  
>altitude: 0  
>reco-type: unknown  
>file-name: img_20171126_235901.474.jpg  

[3f6e0cbe56a62753036f40fa755b0776]: media/neopixel_bluetooth_bb.png
[neopixel_bluetooth_bb.png](media/neopixel_bluetooth_bb.png)
>hash: 3f6e0cbe56a62753036f40fa755b0776  
>timestamp: 19700101T000000Z  
>reco-type: unknown  
>file-name: neopixel_bluetooth_bb.png  

[e43f2d8d317addb9458f1b98fcb76029]: media/img_20171126_235915.149.jpg
[img_20171126_235915.149.jpg](media/img_20171126_235915.149.jpg)
>hash: e43f2d8d317addb9458f1b98fcb76029  
>timestamp: 20171127T075915Z  
>latitude: 38.9083  
>longitude: -77.3918  
>altitude: 0  
>reco-type: unknown  
>file-name: img_20171126_235915.149.jpg  

[bcac705a1303034443e94a70dcb984af]: media/neopixel_bluetooth.fzz
[neopixel_bluetooth.fzz](media/neopixel_bluetooth.fzz)
>hash: bcac705a1303034443e94a70dcb984af  
>timestamp: 19700101T000000Z  
>file-name: neopixel_bluetooth.fzz  

