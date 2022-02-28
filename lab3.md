<p align="center">

  <h3 align="center">Lab 3: Building RF Mixers</h3>

</p>


## Table of contents

- [Authors](#authors)
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Experimental setup](#experimental-setup)
- [Measurements and results](#measurements-and-results)
- [Summary](#summary)


## Authors

Author: Devorah Simon

Lab Partners: Marc Huerta, Ben Sage

## Abstract

A spectrum analyzer and waveform generator were used to measure the output frequencies of a radio frequency (RF) mixer. The design of the RF mixer was chosen to be a double-balanced FET ring mixer. This component may be used in larger devices to change the frequency of some signal while preserving other salient aspects.

## Introduction

In some applications it is desirable to modify a signal's frequency while maintaining its phase and amplitude. An RF mixer can effectively accomplish this task by either upconverting or downconverting to produce shifted signals. The goal of this lab was to learn how to design and build an RF mixer, as well as how to test it, as familiarity with this type of component can be useful in many applications.

## Experimental setup

A wave generator was used to produce the local oscillator (LO) and radio frequency (RF) signals, while a spectrum analyzer was used to measure the intermediate frequency (IF) output.

## Measurements and results

For the initial measurements, the RF signal was 2 MHz and the LO frequency was 10 MHz. As expected, the spectrum analyzer recorded peaks at 10 +/- 2 MHz (8 MHz and 12 MHz), with further harmonics at 28 and 32 MHz. Small spurs can be seen at other even frequencies.

<img width="409" src="https://user-images.githubusercontent.com/22138730/155936240-039ea63f-8148-4b8f-82d6-c027ef1c0c4d.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting the expected mixed signal with peaks at 8 and 12 MHz as well as harmonics)</figcaption>
<br>
<br>
<br>

As the RF signal amplitude was modified, the gain and noise also changed. Below are two photos of the spectrum analyzer, one with an RF amplitude of .5Vpp and one at 1.5Vpp. It is clear from the recorded waveforms that the larger amplitude has both better gain and worse noise.

<img width="409" src="https://user-images.githubusercontent.com/22138730/155937076-65cc2d58-a6c9-4003-8238-aa6fa0d55c4d.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting mixed signal with the RF amplitude at .5Vpp)</figcaption>
<br>
<br>
<br>

<img width="409" src="https://user-images.githubusercontent.com/22138730/155937178-f95579b4-819b-4f1c-b472-72728100920c.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting mixed signal with the RF amplitude at 1.5Vpp)</figcaption>
<br>
<br>
<br>

Changing the amplitude of the LO frequency also significantly affected the gain and noise. Below are two additional photos of the spectrum analyzer, one with an LO amplitude of .5Vpp and one at 3Vpp. It is again clear from the recorded waveforms that the larger amplitude has both better gain and worse noise.

<img width="409" src="https://user-images.githubusercontent.com/22138730/155937707-bf55f8ba-706f-4918-b541-d51308516a8f.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting mixed signal with the LO amplitude at .5Vpp)</figcaption>
<br>
<br>
<br>

<img width="409" src="https://user-images.githubusercontent.com/22138730/155937795-1f0b682f-0882-4941-8fb0-61f462e2d55e.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting mixed signal with the LO amplitude at 3Vpp)</figcaption>
<br>
<br>
<br>

The 1dB compression point for this mixer is located at an RF amplitude of 1.4Vpp. At this point, increasing the amplitude no longer linearly improved the gain, and (as seen in the image above with the 3Vpp amplitude) the noise continued to deteriorate.

<img width="409" src="https://user-images.githubusercontent.com/22138730/155939756-e13d8c8d-9d0a-430d-aca7-677f52425ec8.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting mixed signal with the RF amplitude at 1.4Vpp)</figcaption>
<br>
<br>
<br>

This RF mixer almost "went to DC": that is, a peak was still visible with an IF frequency difference of 20kHz (shown below); however, it was significantly
 more visible at larger IF values.
 
 <img width="409" src="https://user-images.githubusercontent.com/22138730/155940486-31212de6-45f3-4c2b-9c13-7c01775f49b0.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting a very small peak located at 20 kHz)</figcaption>
<br>
<br>
<br>

<img width="409" src="https://user-images.githubusercontent.com/22138730/155940169-a8214174-0c35-43f5-81fb-197483a15795.JPG">
<figcaption align = "center">(photo of spectrum analyzer reading depicting a more easily visible peak located at 100kHz)</figcaption>
<br>
<br>
<br>

## Summary

Mixers are a useful tool for manipulating signals, and familiarity with their design can only help facilitate understanding the next time a mixer is included in a design spec. Using the spectrum analyzer and waveform generators are also crucial skills for testing devices at all stages.

I do not have much experience designing my own components, and so I really appreciated the opportunity to both design and assemble a mixer. I also always appreciate time spent on the spectrum analyzer and waveform generators, since the more practice I get, the better I feel about changing parameters and trying new methods without instruction or supervision. I haven't spent much time soldering surface-mount components, either, and I definitely developed this skill over the many hours of assembly. While it is not the most beautiful piece I've produced, I'm proud of it nevertheless. I've included a photo of my mixer below - despite how tragic the final assembly turned out to be (the transformers aren't even mounted onto the board!) it still accomplished what it needed to.

<img width="409" src="https://user-images.githubusercontent.com/22138730/155941618-5071e76a-7111-45eb-810b-ff7b482e1b48.jpg">
<figcaption align = "center">(photo of mixer as connected to analyzer and generator)</figcaption>
