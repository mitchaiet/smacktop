# Read Me for 0.3 #

This is a wiki version of the README 0.3 file.


## Description ##

SmackTop is a utility for Mac laptops (after 2005) which translates the accelerometer (Sudden Motion Sensor) data into MIDI messages.  This enables the user to control their favorite DAW by smacking their laptop.  The Mac Air series does not (to my knowledge) have an accelerometer…sorry.

SmackTop analyzes the accelerometer's output to detect 'smacks' and classify them into four directions.  Each of these smacks can send a unique MIDI note and/or control change message.

SmackTop was written in Processing.  It is licensed under GNU GPL 2.0, although the included libraries are subject to their own various GNU or CC licenses (see bottom).

## Warning/Disclaimer ##

Smacking your laptop can/may/will damage your computer.  Any damage you do to your computer using this software is your own damn fault.

I have set the default values in SmackTop such that a reasonable **tap** will trigger the **smack** event and mild tilting will move the tilters quickly.  You can change the value of the "Threshold" variable to change the sensitivity of the controllers.  When the threshold is low, the **smack** event can be triggered by simply typing.  When the threshold is high, you really have to punch your computer to trigger the event.  PLOrk has been smacking/tilting laptops for years and has yet to break one while doing so - but its bound to happen.

## Setup ##
1) Setup a MIDI IAC Driver - If you already know what a MIDI IAC Driver is, skip this.

  * Go to your Utilities folder and open "Audio MIDI Setup"
  * Open the  "IAC Driver" window
  * Click the Add Port button (name it something nice if you like)
  * Make sure the "Device is Online" is checked

> For a visual walkthrough: http://www.thecovertoperators.org/Videos/the-iac-driver-osx

2) Run SmackTop\_03.java

3) Choose a MIDI Device:

  * Choose your MIDI device with the "MIDI OUTS" button.  If there are no options available, you didn't do Step 1 right.  Your selected device will be displayed at the bottom of the setup area.

  * Choose your MIDI channel with the "MIDI CHAN #" numberbox.  Currently SmackTop sends all MIDI data over a single channel.  Keys 1-9 toggle between those MIDI channels.

4) Smack away!

  * Make sure you laptop is flat & press 0 to calibrate.  SmackTop also calibrates upon launch.

  * There are four different **smacks** possible in SmackTop 0.3 - Bottom Right/Left and Top Right/Left.  For the bottom hits, you are tapping the edge of the base of the laptop.  For best results, try tapping a few inches in (closer to you) from the headphone port (L) and lock port (R) (Macbook Pro).  For the top hits, you are tapping the edges of the screen.  I've found that its important to have the angle between the screen and the keyboard to be > 90 degrees.  You can play around with how high/low you tap, but I've found the middle of the screen side edge to be most effective.

Note: **Smacks** will not register unless a MIDI device is chosen.  The color of the Smack GUI will change to orange when a **smack** is registered.



## Key Commands ##
  * 1-9 = Switch to midi channels 1-9
  * 0 = calibrate the computer (re-defines what 'flat' is)

## Smack GUI ##
**Threshold Slider:**
Use this slider to change the threshold value of a **smack** event.   The threshold value is displayed in the slider, its default value is 10.

**Hold Time:**
> The minimum amount of time allowed between two **smack** events.  A quantization of sorts.

Each **SMACK** event can trigger either (or both) of the following actions:

**Note #:**
Use the Note # box to change which Note a smack will be sent on.  A **smack** event sends a velocity of 127 on the designated Note.  The box next to this (default ON) toggles whether the Note message is sent.

**CC #:**
Use the CC # box to change which CC a smack will be sent on.  A **smack** event sends a velocity of 127 on the designated CC.  The box next to this (default OFF) toggles whether the CC message is sent.

## Thank You's ##
  * I am greatly indebted to the following Processing libraries and their authors:
    * sms by Daniel Shiffman (& unimotion by Lincoln Ramsay)
    * proMIDI by Christian Riekoff
    * controlP5, oscP5 by Andreas Schegel
    * themidibus by Severin Smith

  * Thanks PLOrk for teaching me how to program and turning me onto all of this. Specifically Dan Trueman, Perry Cook, Rebecca Fiebrink and Ge Wang.

  * Thanks for answers to silly Java questions: Adam Ribaudo, Rebecca Fiebrink, John Brian Kirby

  * Thanks to the monome community for their support.