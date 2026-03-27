## Tinkercad Circuit Link

```
https://www.tinkercad.com/things/bQT0CJUf4ko-nguyen-khoi-nguyenbluesat-sw
```
## Program Explanation
```
- First, I built the circuit with one LED connected to pin 10 using a 220 Ohm resistor and a push button connected to pin 7 with a 10k Ohm resistor
- At the start of each loop, I call idle() to ensure the LED is off and the system is reset to its initial state
- The program then waits for the button to be pressed. Once pressed, I make sure the button is fully released using a while loop and delay(50) for debouncing before entering the armed state
- In armed(), the LED pulses using analogWrite (at pin ~10) to indicate the system is waiting. During this time, the program continuously checks for a button press. If it is detected, it is treated as a false start, triggering false_start() which flashes the LED quickly and restarts the process
- After the armed phase, to make it easier for the user to know when to actually start, I turn off the LED briefly before turning it on instantly as a signal and then trigger reaction()
- In reaction(), the program waits for the user to press the button, measures the reaction time using millis() and prints the attempt number, reaction time, average time and number of false starts
- Based on the reaction time, the LED blinks at different speeds for feedback. I chose a blinking duration of 2.5 seconds so it is clearly visible to the user
- By the way, I use millis() for blinking and pulsing instead of delay() so the program does not stop and can keep running while the LED changes
```
