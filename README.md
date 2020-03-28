# Cherry MX Breakout Boards

![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/switch.gif) 

Two breakout boards designed in **KiCad**. 

Both feature reverse-mounted addressable RGB LED **LTST-A683CEGBW**. 

Both are hot-swap capable (**Kailh Socket** / **Mill-Max 7305**).

Total board dimensions: **26 x 19 mm**.

**Mill-Max 7305 holes are compatible with standalone switches so they can be soldered directly to the board.**

| Schematic | PCB (Kailh Socket) | PCB (Mill-Max 7305) |
|---|---|---|
| ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Schematic.jpg) | ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Kailh%20Socket%20PCB.jpg) | ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Mill-Max%207305%20PCB.jpg) |

## Kailh Socket Renders

| Top View | Bottom View |
|---|---|
| ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Kailh%20Socket%20Top%20View.jpg) | ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Kailh%20Socket%20Bottom%20View.jpg) |

> Kailh Socket 3D Model was obtained from [*QMK*](https://github.com/qmk). All credits go to them. The exact file can be found [here](https://github.com/qmk/qmk_hardware/blob/master/components/kailh_socket_mx.stp).

## Mill-Max 7305 Renders

| Top View | Bottom View |
|---|---|
| ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Mill-Max%207305%20Top%20View.jpg) | ![](https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/Mill-Max%207305%20Bottom%20View.jpg) |

## Real Photos
<table>
 <tbody>
  <tr>
   <td colspan="3"><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real3.jpg"></td>
  </tr>
  <tr>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real2.jpg"></td>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real1.jpg"></td>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real4.jpg"></td>
  </tr>
  <tr>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real5.jpg"></td>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real6.jpg"></td>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/real7.jpg"></td>
  </tr>
 </tbody>
</table>

## Hooking up with Arduino
<table>
 <thead>
  <tr>
   <th>Code</th>
   <th>Wiring diagram</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><pre lang="cpp">
#include "FastLED.h"

    const int ledPin = 6;
    const int buttonPin = 7;

    const int ledSaturation = 255;
    const int ledBrightness = 255;

    CRGB leds[1];

    void setup() {
      pinMode(buttonPin, INPUT_PULLUP);
      FastLED.addLeds<WS2811, ledPin>(leds, 1);
    }

    void loop() {
      int ledHue = 0;
      if(digitalRead(buttonPin) == LOW) ledHue++;

      leds[0].setHSV(ledHue, ledSaturation, ledBrightness);
      FastLED.show();
    }
   </pre></td>
   <td><img src="https://raw.githubusercontent.com/sszczep/Cherry-MX-Breakout-Board/master/images/wiring.jpg"></td>
  </tr>
 </tbody>
</table>

## Datasheets

  * [Cherry MX](https://github.com/sszczep/Cherry-MX-Breakout-Board/blob/master/datasheets/Cherry%20MX.pdf)
  * [LTST-A683CEGBW](https://github.com/sszczep/Cherry-MX-Breakout-Board/blob/master/datasheets/LTST-A683CEGBW.pdf)
  * [Kailh Socket](https://github.com/sszczep/Cherry-MX-Breakout-Board/blob/master/datasheets/Kailh%20Socket.pdf)
  * [Mill-Max](https://github.com/sszczep/Cherry-MX-Breakout-Board/blob/master/datasheets/Mill-Max.pdf)
