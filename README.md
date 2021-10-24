# EOS-OSC
Collection of OSC tools to add to programming and playback productivity in ETC Eos.

## BCF 2000 Touch OSC
I got a Behringer BCF2000 to use as a fader and encoder bank with the Eos software, and though the faders worked pretty well out of the box, getting the encoders to function as parameter encoders was tricky. 
I have done a lot of scripting in TouchOSC to take care of this and have the encoders function as expected. I wrote a parser to take the relative change data from the BCF2000 and convert it into continuous OSC data to send to Eos.
The BCF2000 encoders are set to relative 2 mode for the appropriate control channel.
I also did some scripting to use some encoders as channel and group select, as well as use the buttons above each fader as they are on the iniversal fader wing from ETC, where the bottom one is fire, the top is stop/back, and pressing both is load.
For the faders, there is also some scripting done to make them behave nicely, as Eos' sends the fader level after it is steady at a level for a bit, which is nice to keep the two in sync, but if you fade up and right back down, then it can fight you a bit, so there I wrote a handler to not send the MIDI to the BCF2000 if they are already in sync, only if they are out of sync.
Some of the buttons are set for paging the fader bank, as well as a coarse/fine toggle for encoders, and a select last button.
All this is labeled in the TouchOSC document, as are each of the parameters for all of the encoders.

I have two presets programmed in my BCF2000, one that has most of the parameters for the movers in my theatre, and one for the static LED lights. These parameters can easily be changed in TouchOSC to be whatever you need.

You can program all the control change channels and each of the fader and encoder parameters into the BCF2000 by hand, as I did while I was programming, but you can also upload a sysex file to map all the buttons, faders, and encoders. I have included one that will put in all of my settings into presets 1 and 2 of your BCF2000 (I have all of the MIDI data not being displayed on the BCF2000's display, except for the channel and group select, and the faders set to 0-100, and the encoders set to the relative-2 mode, as well as all the control mapping).
If you already have settings in preset 1 and 2, and want to save these into another preset, you can download the BC Edit software and rearrange which preset is where. Unfortunately, the BC Edit software does not work for uploading sysex to the BCF2000 anymore, but if yo uexport the sysex, you can upload it with another program, such as MIDI-OX. Here is a nice [YouTube tutorial](https://www.youtube.com/watch?v=HD_YZv-8SvQ).
