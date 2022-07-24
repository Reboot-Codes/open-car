---
sidebar_position: 1
---

# OpenFirmware

This is the main thing you need to "use" OpenCar. OpenFirmware is further split into two categories which are the **Master Node** and the **Control Nodes**.

## Master Node

The master node is (most often) a Single Board Computer (like the Raspberry Pi). It runs OFM (OpenFirmware: Master) which orchestrates communication between control nodes and other components (like OpenUI).

## Control Nodes

Control nodes are (usually) micro-controllers. They run OFC (OpenFirmware: Controller) which acts as a "slave" device on both i2C and USB.
