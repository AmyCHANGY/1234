# APDS9960
## I2C Wiring[![Build Status](https://github.com/adafruit/Adafruit_APDS9960/workflows/Arduino%20Library%20CI/badge.svg)](https://github.com/adafruit/Adafruit_APDS9960/actions)

<a href="https://www.adafruit.com/product/3595"><img src="assets/board.jpg?raw=true" width="500px"></a>


## Detect I2C
`sudo i2cdetect -y 1`
## Installing from PyPI
### On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally from PyPI. To install for current user:
`pip3 install adafruit-circuitpython-apds9960`
## Usage Example
```python
    # SPDX-FileCopyrightText: 2021 ladyada for Adafruit Industries
    # SPDX-License-Identifier: MIT

          import time
          import board
          from adafruit_apds9960.apds9960 import APDS9960
          from adafruit_apds9960 import colorutility

          i2c = board.I2C()
          apds = APDS9960(i2c)
          apds.enable_color = True


          while True:
               # create some variables to store the color data in

               # wait for color data to be ready
               while not apds.color_data_ready:
                    time.sleep(0.005)
                    
                    
          print("color temp {}".format(colorutility.calculate_color_temperature(r, g, b)))
          print("light lux {}".format(colorutility.calculate_lux(r, g, b)))
          time.sleep(0.5)
                    )
```
          
          
