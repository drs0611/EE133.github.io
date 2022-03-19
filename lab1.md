<p align="center">

  <h3 align="center">Lab 1: Self resonance of various components</h3>

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

The self-resonant frequencies of a capacitor and inductor were measured using a vector network analyzer (VNA). The graphs produced by the VNA software were inspected for data indicating parasitic reactances. This technique can be used to ensure more accurate circuit models.


## Introduction

Components have varying self-resonance frequencies, after which point they will no longer behave as expected. For example, after a capacitor's self-resonance frequency, it will begin to behave as though it was actually an inductor. If a component's self-resonance frequency is not known and accidentally overshot, it can be difficult to debug. The goal of this lab was to learn how to find the self-resonance frequency of a given component, as this is a useful skill for later projects.

## Experimental setup

In order to use the NanoVNA's included cables, we soldered connectors to a piece of copper clad. From there, we connected components to those connectors to aid in ease of measurement.

## Measurements and results

For the first capacitor measured, the self resonance frequency was at 51.51 MHz, as indicated by both the Smith chart and the graph offered by the Nano VNA. As the frequency parameter swept from 1 MHz to 100 MHz, the Smith chart's line indicating reactace vs frequency moved from the capacitve reactance (lower) half into the inductive reactance (upper) half. 

<img width="409" alt="Screen Shot 2022-02-09 at 9 28 07 PM" src="https://user-images.githubusercontent.com/22138730/153344499-cdbd4415-3913-4f7e-af08-3480f5884078.png">
<figcaption align = "center"><b>(Fig. 1: screenshot of nanovna measurement depicting Smith chart of capacitor's reactance at varying frequencies)</b></figcaption>
<br><br><br>

The log graph showed a descending line depicting conductance until the 50 MHz frequency, at which point it began to rise, indicating a change to inductance (that is, the capacitor after its self-resonance frequency began to act as an inductor).

<img width="407" alt="Screen Shot 2022-02-07 at 2 53 50 PM" src="https://user-images.githubusercontent.com/22138730/153344545-d2654475-9a12-4cb6-97d8-26c6643191bf.png">
<figcaption align = "center"><b>(Fig. 2: screenshot of nanovna measurement depicting log graph of capacitor's response at varying frequencies)</b></figcaption>
<br><br><br>

For the inductor, the self resonance frequency was at 393.88 MHz, as indicated by the Smith chart. As the frequency parameter swept from 100 MHz to 1000 MHz, the Smith chart's line moved from the inductive reactance (upper) half into the capacitive reactance (lower) half.

<img width="404" alt="Screen Shot 2022-02-07 at 3 03 04 PM" src="https://user-images.githubusercontent.com/22138730/153344558-708b8d08-7360-4c9b-b723-7b63cf734df0.png">
<figcaption align = "center"><b>(Fig. 3: screenshot of nanovna measurement depicting Smith chart of inductor's reactance at varying frequencies)</b></figcaption>
<br><br><br>

These measurements were unexpected, given that it is not unreasonable for one to anticipate that a conductor and an inductor to act as such at all frequencies from a theoretical standpoint. However, all circuit models must take into account the parasitics that are unavoidable with physical components. Ascertaining the self-resonance frequency of individual components will help to ensure more accurate designs.

## Summary

Parasitics can be a difficult thing to debug, but understanding the concepts behind self resonance can aid greatly in achieving a robust final product. Determining the self-resonance frequency of components in this manner is straightforward and helps to put physical practice to the theory commonly taught and subsequently overlooked.

This was my first time using a Smith chart, and I appreciated that the design of the experiment introduced some of the most fundamental concepts (inductance/conductance, traveling along the lines) in a very clear way that could be mapped directly to the procedures being run. It was fascinating to see a conductor act as an inductor and vice versa, as this was something that had only been mentioned in passing in my classes. I was previously under the impression that this was a rare occurrance and not something to worry about. However, I now see how simple it is to check the self-resonance frequency of a component and ensure that the piece I am using is appropriate for the job.

