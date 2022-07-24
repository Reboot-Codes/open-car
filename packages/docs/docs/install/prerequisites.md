# Prerequisites

Before you start the installation of OpenCar, you'll need to prepare. This will involve messing with your car's internals; if you aren't comfortable with with that, you should probably stop here.

First will be preparing the car, and seeing if it's compatible with an existing configuration of OpenCar. (If it isn't we'll go over creating one, if you're up to it.) Procuring custom parts to keep our custom computer system in place. Then flashing the OS and firmware to the custom computer. Installing the custom computer. Finally, testing it all out.

Many modern cars use multiple different "computers" (more accurately, micro-controllers), usually one for each system. OpenCar replaces all of them with off-the-shelf components and adds a "Master Node" to orchestrate them. This also provides a central interface to modify configuration and diagnose problems.

OpenCar (at minimum) will replace your car's existing Engine Control Module (or ECM). Your car's ECM usually controls:

- Fuel to Air Ratio
- Starter
- Spark Plugs
- and Lubrication (electric)

However it may be controlling other aspects of your engine.

## Emissions

OpenCar is designed to help you to have better control over your vehicle, but we also recommend adhering to the emissions requirements for your area (state, in the US). You should keep in mind these requirements when installing and configuring OpenCar.

## Bill of Materials

As with any other custom modification to your car, you'll need to either purchase or create parts to complete the install. You will probably want to either 3D print the custom brackets and trim pieces, or have them made then shipped to you. (And make sure to share your designs if you make them, it saves everybody else a lot of time and filament!)

### Required Parts

- Holding Bracket(s)
  - This allows us to use the existing mounting hardware in your car to hold our custom electronics. You'll need one for the Master and each micro-controller.
- Wiring Adapter(s)
  - Many modern cars use proprietary connectors to (well) connect sensors and mechanisms to the car computer. This becomes a problem for interfacing OpenCar with the actual car hardware.
- Single Board Computer
  - We recommend using a [Raspberry Pi 4 B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/), due to it's high popularity and ease of use/development. Although you could also use a different board with GPIO pins to connect over [i2C](https://en.wikipedia.org/wiki/I%C2%B2C) and USB (USB is only used for debugging and reprogramming).
- Micro Controller(s)
  - These actually replace the pre-existing "computers" that your car uses to monitor and manage it's systems. We recommend using [Adafruit Feather](https://www.adafruit.com/category/943) boards due to their standardized dimensions. (We especially like boards with [Stemma (QT)](https://www.adafruit.com/category/1005) connectors as they are compatible with/use i2C.)

### Optional Parts

- 3D Printer
  - Having one is especially useful when prototyping new brackets or trim pieces. And you can use it for other projects too.
- Infotainment Assembly
  - This allows you to use OpenUI to configure and monitor your car. (Instead of just using OpenDiagnostics.) You could use an [alphanumeric LCD](https://www.adafruit.com/product/499) and [rotary encoder](https://www.adafruit.com/product/5221) (plus some buttons). Or you can use a display like [this](https://www.adafruit.com/product/2260) or [this](https://www.adafruit.com/product/2407) instead to have a fancy touch screen (maybe even [CarPlay](https://www.apple.com/ios/carplay/) or [Android Auto](https://www.android.com/auto/)).
  - You could also use this in place of your radio (if you choose to add a tuner to the master).
