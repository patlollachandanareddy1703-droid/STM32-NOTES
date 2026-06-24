# PWM Notes

## What is PWM?
Pulse Width Modulation (PWM) is a technique used to control the average voltage delivered to a load.

## Duty Cycle
It is defined as the percentage of time for which the wave is in active state 
Duty Cycle = (ON Time / Total Time) × 100

## Frequency
PWM Frequency = 1 / Time Period

## Resolution
Resolution determines the number of duty cycle levels available. As the resolution increases the time required to count or overall time consumed to perform an action also increases Apart from that increasing resolution enables the user to control the task more precisely with required duty cycle .
if the resolution is confined to 3,then the duty cycle is limited to consined numbers 

## Measurement of output voltage 
Practically the output voltage is not same as the maximum voltage represented in the graph or CRO,the output voltage depends on the duty cycle  on increasing the duty cycle the output voltage increases approaching the maximum voltage based on this feature many applications are designed as mentioned below

Vout = (duty cycle(in %)*Maximum voltage)/100

## Calculation of PWM frequency
if given System Clock is 72 MHZ and 8 bit resolution then
72 MHZ represents we can count 72 million times each second
8 bit resolution represents Each cycle is 256 counts 

It is clearly  shown in image ="Screenshot 2026-06-07 210948" src="https://github.com/user-attachments/assets/dda6177f-8c37-4a1c-b2e0-76caf680f621" />
<img width="790" height="298" alt

PWM frequency = system clock/no; of counts 

## Applications
we generally use the function analgWrite(pin,duty cyle ) to control the tasks as below
- LED brightness control
- Motor speed control
- Servo motor control

## STM32 PWM
STM32 timers can generate PWM signals on output pins.
