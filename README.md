<h3 align="center">Arduino library for PCA9551</h3>

<div align="center">

[![Build Status](https://travis-ci.org/Savjee/arduino-pca9551.svg?branch=master)](https://travis-ci.org/Savjee/arduino-pca9551)
[![GitHub Issues](https://img.shields.io/github/issues/Savjee/arduino-pca9551.svg)](https://github.com/Savjee/arduino-pca9551/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/Savjee/arduino-pca9551.svg)](https://github.com/Savjee/arduino-pca9551/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

*Arduino library for the [PCA9551](https://www.nxp.com/docs/en/data-sheet/PCA9551.pdf) i2c LED Driver. Supports on/off and PWM.*

*🧪This is work in progress.*

---

## ⛏️ How to use

Start by installing the library and including it in your sketch. Also don't forget to import `Wire` and initialize the i2c bus:
```cpp
#include <PCA9551.h>
#include <Wire.h>


// Initialize i2c
Wire.begin();
```

Create a new instance of the LED driver. Possible addresses are `PCA9551_ADDR_1` until `PCA9551_ADDR_8` (which is `0x60` to `0x67`):

```cpp
PCA9551 ledDriver = PCA9551(PCA9551_ADDR_1);
```

Now you can manipulate the LEDs:

```cpp
ledDriver.turnAllOn();
ledDriver.turnAllOff();

ledDriver.setLedState(0, LED_ON);
ledDriver.setLedState(0, LED_OFF);
```

The `setLedState` function takes two arguments: the index of the led you want to control and the new state for that LED.

## 😠 Limitations
* PWM support has not been tested yet (although some code is already set up)
* When using `setLedState` you can only control 1 LED, all others will be turned off by default.

## ✍️ Contribute
Feel free to fork this project, open issues and submit pull requests!