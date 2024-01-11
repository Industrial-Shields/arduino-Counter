# arduino-Counter

The Counter library provides a way of counting rising edges until a defined preset value.

## Gettings started

### Prerequisites
1. The [Arduino IDE](http://www.arduino.cc) 1.8.0 or higher
2. The [Industrial Shields Arduino boards](http://blog.industrialshields.com/en/installing-industrial-shields-equipment-to-the-arduino-ide/) (optional, used in the examples)

### Installing
1. Download the [library](https://github.com/Industrial-Shields/arduino-Counter) from the GitHub as a "ZIP" file.
2. From the Arduino IDE, select the downloaded "ZIP" file in the menu "Sketch/Inlcude library/Add .ZIP library".
3. Now you can open any example from the "File/Examples/Counter" menu.


## Usage

```c++
#include <Counter.h>

Counter C(100);
```

The `Counter` returns HIGH when the internal counter is equal to the preset value.

```c++
int up = digitalRead(I0_0);
int down = digitalRead(I0_1);
int reset = digitalRead(I0_2);
if (C.update(up, down, reset, preset) == HIGH) {
    // Enter here when the counter is equal to 100
	// The counter counts up when I0.0 rises
	// The counter counts down when I0.1 rises
	// The counter is set to zero when I0.2 is HIGH
}
```
