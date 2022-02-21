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

In this lab, a capacitor and an inductor were connected to a NanoVNA to attempt to locate their self-resonance frequency. Connectors were soldered to copper clad in order to use the NanoVNA's included cables. The graphs produced by the VNA software were scanned to find the components' self-resonance frequencies.

## Introduction

Components have varying self-resonance frequencies, after which point they will no longer behave as expected. For example, after a capacitor's self-resonance frequency, it will begin to behave as though it was actually an inductor. If a component's self-resonance frequency is not known and accidentally overshot, it can be difficult to debug. The goal of this lab was to learn how to find the self-resonance frequency of a given component, as this is a useful skill for later projects.

## Experimental setup

We connected the components to connectors soldered to a piece of copper clad to aid in ease of measurement.

## Measurements and results

For the first capacitor measured, the self resonance frequency was at 51.51 MHz, as indicated by both the Smith chart and the graph offered by the Nano VNA. As the parameters swept from 1 MHz to 100 MHz, the Smith chart's line moved from the conductance (lower) half into the inductance (upper) half. 

<img width="409" alt="Screen Shot 2022-02-09 at 9 28 07 PM" src="https://user-images.githubusercontent.com/22138730/153344499-cdbd4415-3913-4f7e-af08-3480f5884078.png">
<figcaption align = "center"><b>(screenshot of nanovna measurement depicting conditions described above)</b></figcaption>

The log graph showed a descending line depicting conductance until the 50 MHz frequency, at which point it began to rise, indicating a change to inductance (that is, the capacitor after its self-resonance frequency began to act as an inductor).

<img width="407" alt="Screen Shot 2022-02-07 at 2 53 50 PM" src="https://user-images.githubusercontent.com/22138730/153344545-d2654475-9a12-4cb6-97d8-26c6643191bf.png">
<figcaption align = "center"><b>(screenshot of nanovna measurement depicting conditions described above)</b></figcaption>

For the inductor, the self resonance frequency was at 393.88 MHz, as indicated by the Smith chart. As the parameters swept from 100 MHz to 1000 MHz, the Smith chart's line moved from the inductance (upper) half into the conductance (lower) half.

<img width="404" alt="Screen Shot 2022-02-07 at 3 03 04 PM" src="https://user-images.githubusercontent.com/22138730/153344558-708b8d08-7360-4c9b-b723-7b63cf734df0.png">
<figcaption align = "center"><b>(screenshot of nanovna measurement depicting conditions described above)</b></figcaption>

## Summary

Parasitics can be a difficult thing to debug, but understanding the concepts behind self resonance can aid greatly in achieving a robust final product. Determining the self-resonance frequency of components in this manner is straightforward and helps to put physical practice to the theory commonly taught and subsequently overlooked.

This was my first time using a Smith chart, and I appreciated that the design of the experiment introduced some of the most fundamental concepts (inductance/conductance, traveling along the lines) in a very clear way that could be mapped directly to the procedures being run. It was fascinating to see a conductor act as an inductor and vice versa, as this was something that had only been mentioned in passing in my classes. I was previously under the impression that this was a rare occurrance and not something to worry about. However, I now see how simple it is to check the self-resonance frequency of a component and ensure that the piece I am using is appropriate for the job.

