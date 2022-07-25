# Writing Custom Firmware

The whole point of OpenCar was to have more technically inclined (in terms of both software and car hardware) to write firmware for vehicles that might benefit from a modern management system or are in need of repair by someone who doesn't want to pay others to flash proprietary software on something they don't/can't understand.

A lot of OpenCar is written in CircuitPython (a fork of MicroPython). So, if you can read Python, you can read CircuitPython. Even the OFM is (technically) written in CircuitPython. (Mainly because it allows you to use a different SBC without having to change the source code.)

OpenUI is written in TypeScript and TSX (a.k.a. TypeScript JSX) and uses React. This allows OpenUI to work anywhere that has network access to the Master Node. (Which means you don't have to just run OpenUI on the master node, but we like to because it means less troubleshooting and/or complexity.)

OpenDiagnostics is also written in TypeScript and TSX. The mobile app just points to the master node's OpenDiagnostics web server. But it's nice to have anyways.
