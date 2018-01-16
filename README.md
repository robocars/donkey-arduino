# donkey-arduino
Arduino companion for Donkey car.
For now, the following feature is implemented :

# PWM Proxy for Arduino

Simple Arduino based PWM proxy. It is used to get the PWM orders received from Tx and sent it to the Raspberry through serial port.
It outputs last measured pwm signal each 50ms

output format is :
`<timestamp>`,`<pwm throttle>`,`<pwm_steering>`,`<pwm_freq>`
where :
* `<timestamp>` is a monotonic timestamp counter used to check fo real time issue ( number of milliseconds since the Arduino board began running the current program)
* `<pwm_throttle>` is the pwm duration of the throttle signal, in us
* `<pwm_steering>` is the pwm duration of the steering signal, in us
* `<pwm_freq`> is the perceived pwm frequency.

When the algorithm is unable to detect the pwm signal, it ouputs :
`<timestamp>`,-,-,-

Inspired from  http://www.benripley.com/diy/arduino/three-ways-to-read-a-pwm-signal-with-arduino/ for other way.
