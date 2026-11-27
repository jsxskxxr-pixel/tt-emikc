## How it works

This circuit reads a two-bit code on IN3 and IN2. OUT1 through OUT4 show 01, 10, 11, and 00, respectively. OUT0 goes high when IN0 and IN1 are both high.

It can save one code at a time. On a rising clock edge, IN4 writes a code if the store is empty. OUT7 goes high to show a code is waiting. IN5 acknowledges that code on the next rising edge. If IN4 and IN5 are high together, the new code replaces the old one.

## How to test

Hold RST_N low, pulse CLK, then bring RST_N high. Set IN3 and IN2 to a code. Set IN4 high and pulse CLK. Check the saved bits on OUT6 and OUT5 and the flag on OUT7. Change the input code and pulse CLK again to see the saved code hold. Lower IN4, raise IN5, and pulse CLK to clear OUT7. The saved bits keep their last values until another write or reset.

## External hardware

Use switches or a digital input source to set the inputs. LEDs or a logic analyzer can show the outputs. The Wokwi demo uses a seven-segment display as eight separate indicators.
