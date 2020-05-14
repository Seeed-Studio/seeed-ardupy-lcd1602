# Seeed ArduPy LCD1602 [![Build Status](https://api.travis-ci.com/Seeed-Studio/seeed-ardupy-lcd1602.svg?branch=master)](https://travis-ci.com/github/Seeed-Studio/seeed-ardupy-lcd1602)

## Introduction

Done with the tedious mono color backlight? This Grove - LCD RBG Backlight enables you to set the color to whatever you like via the simple and concise Grove interface. It takes I2C as the communication method with your microcontroller. The number of pins required for data exchange and backlight control shrinks from ~10 to 2, relieving IOs for other challenging tasks. In addition, Grove - LCD RGB Backlight supports user-defined characters. Want to get a love heart or another custom character? Just take advantage of this feature and design it!

You can get more information in here [Grove - LCD RGB Backlight](https://wiki.seeedstudio.com/Grove-LCD_RGB_Backlight/).

![Seeed ArduPy LCD1602](https://files.seeedstudio.com/wiki/Grove_LCD_RGB_Backlight/images/intro.jpg)

## How to binding with ArduPy
- Install [AIP](https://github.com/Seeed-Studio/ardupy-aip)
```shell
pip3 install aip
```
- Build firmware with Seeed ArduPy LCD1602
```shell
aip install https://github.com/Seeed-Studio/seeed-ardupy-lcd1602
aip build
```
- Flash new firmware to you ArduPy board
```shell
aip flash [Ardupy Bin PATH]
```
For more examples of using AIP, please refer to [AIP](https://github.com/Seeed-Studio/ardupy-aip).
## Usage
```python
from arduino import grove_lcd1602
import time

lcd = grove_lcd1602()

lcd.print("Hello world.")
lcd.is_blink_cursor = True
i = 0

while True:
    lcd.set_cursor(1, 2) #column 1, row 2
    lcd.print(i)
    time.sleep(0.5)
    i = i + 1
```



## API Reference

- **clear(*void*) : void** - clear display.
```python
lcd.clear() # clean lcd display
```
- **set_cursor(*column<uint8_t>, row<uint8_t>*) : void** - set cursor.
```python
lcd.set_cursor(16, 1)
```
- **print(*arg<int/float/string>*) : void** - print.
```python
lcd.print(1) # print int
lcd.print(3.14) # print float
lcd.print("Hello world.") # print string
```
- **is_blink_cursor** - set cursor blink or not.
```python
lcd.is_blink_cursor = True  # set cursor blink
lcd.is_blink_cursor = False  # set cursor no blink
```

----
## License
This software is written by seeed studio<br>
and is licensed under [The MIT License](http://opensource.org/licenses/mit-license.php). Check License.txt for more information.<br>

Contributing to this software is warmly welcomed. You can do this basically by<br>
[forking](https://help.github.com/articles/fork-a-repo), committing modifications and then [pulling requests](https://help.github.com/articles/using-pull-requests) (follow the links above<br>
for operating guide). Adding change log and your contact into file header is encouraged.<br>
Thanks for your contribution.

Seeed Studio is an open hardware facilitation company based in Shenzhen, China. <br>
Benefiting from local manufacture power and convenient global logistic system, <br>
we integrate resources to serve new era of innovation. Seeed also works with <br>
global distributors and partners to push open hardware movement.<br>
