<p align="center">

  <h3 align="center">Lab 2: Generating waveforms with the Si5351</h3>

</p>


## Table of contents

- [Authors](#authors)
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Measurements and results](#measurements-and-results)
- [Summary](#summary)


## Authors

Author: Devorah Simon

Lab Partners: Marc Huerta, Ben Sage

## Abstract

In this lab, a microprocessor was used to control a clock generator with the intent of producing three distinct waveforms. The waveforms were then measured using an oscilloscope and spectrum analyzer to verify the program output.

## Introduction

The Si5351 clock generator chip has a 25MHz crystal reference that with the advertised ability to generate a waveform with any frequency between 8 KHz and 150 MHz. It has three separate outputs that can generate distinct, independent waveforms. There were two goals to this lab: first, to understand how to use a clock generator to replace crystals/crystal oscillators, and second, to practice using an embedded microprocessor to control some device with output, as both are useful skills for later projects.

## Measurements and results

A Python program was run on the embedded microprocessor (Itsy Bitsy) to produce varying frequencies on the Si5351 clock generator. Commented code can be found at [here](https://learn.adafruit.com/adafruit-si5351-clock-generator-breakout/circuitpython), and uncommented code can be found below:

```
# SPDX-FileCopyrightText: 2021 ladyada for Adafruit Industries
# SPDX-License-Identifier: MIT

import board
import busio
import adafruit_si5351

i2c = busio.I2C(board.SCL, board.SDA)
si5351 = adafruit_si5351.SI5351(i2c)
si5351.pll_a.configure_integer(36)  # Multiply 25mhz by 36
print("PLL A frequency: {0}mhz".format(si5351.pll_a.frequency / 1000000))
si5351.pll_b.configure_fractional(24, 2, 3)  # Multiply 25mhz by 24.667 (24 2/3)
print("PLL B frequency: {0}mhz".format(si5351.pll_b.frequency / 1000000))
si5351.clock_0.configure_integer(si5351.pll_a, 8)
print("Clock 0: {0}mhz".format(si5351.clock_0.frequency / 1000000))
si5351.clock_1.configure_fractional(si5351.pll_b, 45, 1, 2)  # Divide by 45.5 (45 1/2)
print("Clock 1: {0}mhz".format(si5351.clock_1.frequency / 1000000))
si5351.clock_2.configure_integer(si5351.pll_b, 900)
si5351.clock_2.r_divider = adafruit_si5351.R_DIV_64
print("Clock 2: {0}khz".format(si5351.clock_2.frequency / 1000))

si5351.outputs_enabled = True
```

The first measurements were taken on the oscilloscope. As the same Python program could independently produce three distinct waveforms, three separate oscilloscope readings were generated, with frequencies of 112.5mhz, 13.5531mhz, and 10.76khz. The images are shown below:

<img width="409" alt="clock 0 oscilloscope" src="https://user-images.githubusercontent.com/22138730/155463067-038566b1-d793-4263-a12d-2a0eec9f90fc.jpg">
<figcaption align = "center"><b>(photo of oscilloscope reading depicting the intended 112.5 MHz waveform (actual frequency measured 111.86 MHz))</b></figcaption>
<br>
<br>
<br>
<img width="409" alt="clock 1 oscilloscope" src="https://user-images.githubusercontent.com/22138730/155463238-d92daa4f-5929-4335-9fe8-f42eb50ccfae.jpg">
<figcaption align = "center"><b>(photo of oscilloscope reading depicting the intended 13.5531 MHz waveform (actual frequency measured 13.51 MHz))</b></figcaption>
<br>
<br>
<br>
<img width="409" alt="clock 2 oscilloscope" src="https://user-images.githubusercontent.com/22138730/155463412-ded5a562-61c6-4f5a-94d3-c2a707273a6e.jpg">
<figcaption align = "center"><b>(photo of oscilloscope reading depicting the intended 10.76 kHz waveform (actual frequency measured 10.71 kHz))</b></figcaption>
<br>
<br>
<br>
The second set of measurements were taken using the spectrum analyzer. The same frequencies were sampled:

<img width="409" alt="clock 0 spectrum analyzer" src="https://user-images.githubusercontent.com/22138730/155466923-2369d930-d829-481c-909e-911f7a8abab3.jpg">
<figcaption align = "center"><b>(photo of spectrum analyzer reading depicting the intended 112.5 MHz waveform (peak measured at 112 MHz))</b></figcaption>
<br>
<br>
<br>
<img width="409" alt="clock 1 spectrum analyzer" src="https://user-images.githubusercontent.com/22138730/155466930-5aad612e-d662-49d7-a45b-5ad9cc74ccb8.jpg">
<figcaption align = "center"><b>(photo of spectrum analyzer reading depicting the intended 13.5531 MHz waveform (peak measured at 13.562 MHz))</b></figcaption>
<br>
<br>
<br>
<img width="409" alt="clock 2 spectrum analyzer" src="https://user-images.githubusercontent.com/22138730/155466935-98d8f649-4f34-45cd-8551-85ced9a5bbdb.jpg">
<figcaption align = "center"><b>(photo of spectrum analyzer reading depicting the intended 10.76 kHz waveform (peak measured at 10.690 kHz))</b></figcaption>
<br>
<br>
<br>

## Summary

Clock generators have all but replaced crystals when timing components, due to their wide range of available frequency generation, relatively smaller amount of space required, and lower cost relative to using multiple or high frequency crystals.

I don't think I've ever used a clock generator before this lab, and I certainly did not use one just for the sake of experimenting with frequencies. While the oscilloscope and spectrum analyzer served mostly to confirm that the clock generator was indeed producing waveforms of the desired frequencies, it was nevertheless rewarding to see that the program was working as intended.


