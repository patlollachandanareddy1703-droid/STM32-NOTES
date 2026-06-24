## What are Timers
Timer is a built in peripheral that acts like a highly accurate counter

## Advantage
We use Timers to eliminate the disadvantage  of using delay in while loop which completely block CPU from doing any other work.

## Configuration
Mainly it contains prescalar and ARR (which represents Counter Period)
Prescalar is used to adjust the frequency as required from the actual system clock frequency (0 to 65536)
 eg:Let us assume the system frequency is 72MHZ but now i what the timer to behave with 1MHZ as per my requirement 
 for this divide as shown
                Time Tick(time taken by 1 tick)   =   72/(PSC+1)     ; where PSC is 71 
ARR is Auto Reload Range (0 to 65536 for 16 bit microcontroller) .Generally ARR defines how many ticks you want 
based on the time 

## How to use Timers 
eg:If you want to take action for every 1 sec ,then you should adjust the values of prescalar and ARR so that time tick doesnt 
exceed the range 
  if we consider time tick for every 1ms which is basic ,the prescalar value will be 71999 which is out of range
  so let us assume as prescalar as 7200 (7199) 
     then time tick is 10KHZ ;0.1ms  or 100us
     To complete 1sec ,timer requires 10000 ticks which is in range 
     This 10000 tick is the value of ARR i.e; 0 to 9999
     when the timer overflows the arr range it call a function that need to be run for every 1 sec 

## Main functions in code
HAL_TIM_Base_Start_IT(&htim1);  //to start the timer
HAL_TIM_PeriodElapsedCallback(TIM_HandleTypeDef*htim)  // to call function after overflows ARR range 
{
 if(htim -> Instance == TIM1)
 {
  // write the function to be performed (eg:to blink the led)
 }
}
                                            
