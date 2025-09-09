# open_fingi_project
An Open-Source Project to Train your Finger Strength

## Introduction

This project is a compilation of software, hardware and documentation to build your own finger strength trainer.

This project has three parts:

- a UI: the [fresh_fingi](https://github.com/1ucky40nc3/fresh_fingi)
- hardware instructions and microcontroller code: [hardcore_fingi](https://github.com/1ucky40nc3/hardcore_fingi)
- CAD documents: [Open Fingi Project V1](https://cad.onshape.com/documents/5c349e864819a3f7aafa01c6/w/9176c294fd9164e69fcd1a26/e/8c77ec7fedf361c3332a9188)

All three parts are designed to work together - at least in some versions. Here comes the hard news: 

> This is a hobby project and only supported/developed by me!

My goal is to use this project as a fun learning experience. As part of the learning I am trying to improve my skills in documenting such a project and my design decisions.

> Please don't expect complete instructions to get everything going smoothly!

## Getting Started

To get started you will have to look into the projects yourself - sorry. Each part should provide you with enough information to get you going. Please refer to the GitHub repositories or CAD files in the compatible versions.

### Confirmed Version Compatiblity

For the following versions of the UI, hardware and CAD parts I have confirmed the version compatiblity:

| [open_fingi_project](https://github.com/1ucky40nc3/open_fingi_project)         | [fresh_fingi](https://github.com/1ucky40nc3/fresh_fingi)                | [hardcore_fingi](https://github.com/1ucky40nc3/hardcore_fingi)             | [Open Fingi Project V1](https://cad.onshape.com/documents/5c349e864819a3f7aafa01c6/v/b8586a586bc7e66ccaa9be95/e/8c77ec7fedf361c3332a9188?showReturnToWorkspaceLink=true) |
|--------------------------------------------------------------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [v0.0.1](https://github.com/1ucky40nc3/open_fingi_project/releases/tag/v0.0.1) | [v0.0.1](https://github.com/1ucky40nc3/fresh_fingi/releases/tag/v0.0.1) | [v0.0.1](https://github.com/1ucky40nc3/hardcore_fingi/releases/tag/v0.0.1) | [v0.0.1](https://cad.onshape.com/documents/5c349e864819a3f7aafa01c6/v/b8586a586bc7e66ccaa9be95/e/8c77ec7fedf361c3332a9188?showReturnToWorkspaceLink=true)                |


## Documentation

### Architecture

The architecture of this project is quite simple:

A sensor contraption (we will refer to this as fingi below) that sends data and recieves controls. Additionally an app that establishes the bluetooth connection and controls. The app also displays the sensor data.

The fingi creates a bluetooth server. A compatible Bluetooth Low Energy  (BLE) device will serve as the client (via the app). The communication is done vis the Generic ATTribute Profile (GATT).

#### GATT Transacrions

The GATT transactions are also meant to be quite simple. We have one service. This service has multiple characteristics:

- a read-only (notify) characteristic for the sensor time series data (just floats)
- a read-only (notify) characteristic for the battery charge (a boolean that indicates a low battery charge)
- a read/write (notify) property to trigger taring


