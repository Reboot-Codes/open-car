# Prerequisites

Before you start the installation of OpenCar, you'll need to prepare. This will involve messing with your car's internals; if you aren't comfortable with with that, you should probably stop here.

First will be preparing the car, and seeing if it's compatible with an existing configuration of OpenCar. (If it isn't we'll go over creating one, if you're up to it.) Procuring custom parts to keep our custom computer system in place. Then flashing the OS and firmware to the custom computer. Installing the custom computer. Finally, testing it all out.

Many modern cars use multiple different "computers" (more accurately, micro-controllers), usually one for each system. OpenCar replaces all of them with off-the-shelf components and adds a "Master Node" to orchestrate them. This also provides a central interface to modify configuration and diagnose problems.

## What OpenCar Does

OpenCar (at minimum) will replace your car's existing Engine Control Module (or ECM). Your car's ECM usually controls:

- Fuel Pump
- Fuel Injectors
- Starter
- Spark Plugs
- Lubrication
- Cooling and more...

OpenCar can also replace your car's Body Control Module (or BCM). This may not be found on some vehicles, but it (most of the time) controls:

- Overhead Lighting
- Instrument Cluster
- Headlights
- Blinkers
- Reverse Camera and more...

OpenCar can also be used instead of your infotainment center (a.k.a. radio). That's slightly more advanced, and is covered later in this guide.

## Emissions

OpenCar is designed to help you to have better control over your vehicle, but we also recommend adhering to the emissions requirements for your area (state, in the US). You should keep in mind these requirements when installing and configuring OpenCar.

Most (depending on the laws in your area) emission standards are based on the vehicle's year. Therefore base your requirements on that. For fully custom vehicles (e.g. something you built in your backyard) we recommend going with the emission requirements for the current vehicle year. (Yeah, vehicle years aren't synced with normal years for some reason.)

:::note

As with anything here, **this is not legal advice**! Do your own research and/or talk to a lawyer to make sure you're following the law.

:::

## Bill of Materials

As with any other custom modification to your car, you'll need to either purchase or create parts to complete the install. You will probably want to either 3D print the custom brackets and trim pieces, or have them made then shipped to you. (And make sure to share your designs if you make them, it saves everybody else a lot of time and filament!)

### Required Parts

- Holding Bracket(s)
  - This allows us to use the existing mounting hardware in your car to hold our custom electronics. You'll need one for the Master and each micro-controller.
- Wiring Adapter(s)
  - Many modern cars use proprietary connectors to (well) connect sensors and mechanisms to the car computer. This becomes a problem for interfacing OpenCar with the actual car hardware.
- Single Board Computer
  - We recommend using a [Raspberry Pi 4 B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/), due to it's high popularity and ease of use/development. Although you could also use a different board with GPIO pins to connect over [i2C](https://en.wikipedia.org/wiki/I%C2%B2C) and [USB](https://en.wikipedia.org/wiki/USB) (USB is only used for debugging and reprogramming).
- Micro Controller(s)
  - These actually replace the pre-existing "computers" that your car uses to monitor and manage it's systems. We recommend using [Adafruit Feather](https://www.adafruit.com/category/943) boards due to their standardized dimensions. (We especially like boards with [Stemma (QT)](https://www.adafruit.com/category/1005) connectors as they are compatible with/use i2C.)

:::caution

Some micro-controllers are not compatible with CircuitPython. OpenFirmware is written in CircuitPython! Check if the micro-controller you are planning to use is compatible with CircuitPython: <https://circuitpython.org/downloads>

:::

- i2C and USB Cables
  - As was mentioned above, OpenFirmware uses i2C and USB to communicate between nodes. If you aren't using an Adafruit board with Stemma (QT) connectors, we still recommend using them due to their small size and ease of use. For USB, we strongly recommend using USB-C due to it being mostly future-proof, EU compliant, small, and reversible.

### Optional Parts

- 3D Printer
  - Having one is especially useful when prototyping new brackets or trim pieces. And you can use it for other projects too.
- Infotainment Assembly
  - This allows you to use OpenUI to configure and monitor your car. (Instead of just using OpenDiagnostics.) You could use an [alphanumeric LCD](https://www.adafruit.com/product/499) and [rotary encoder](https://www.adafruit.com/product/5221) (plus some buttons). Or you can use a display like [this](https://www.adafruit.com/product/2260) or [this](https://www.adafruit.com/product/2407) instead to have a fancy touch screen (maybe even [CarPlay](https://www.apple.com/ios/carplay/) or [Android Auto](https://www.android.com/auto/)).
  - You could also use this in place of your radio (if you choose to add a tuner to the master).
