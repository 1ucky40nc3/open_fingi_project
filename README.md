# open_fingi_project
An Open-Source Project to Train your Finger Strength

## Introduction

This project is a compilation of software, hardware and documentation to build your own finger strength trainer.

## Documentation

### Architecture

The architecture of this project is quite simple:

A sensor contraption (we will refer to this as fingi below) that sends data and recieves controls. Additionally an app that establishes the bluetooth connection and controls. The app also displays the sensor data.

The fingi creates a bluetooth server. A compatible Bluetooth Low Energy  (BLE) device will serve as the client (via the app). The communication is done vis the Generic ATTribute Profile (GATT).

#### GATT Transacrions

TODO

