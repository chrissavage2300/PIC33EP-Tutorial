ADC must be set for Auto Sampling. Conversion Trigger must be "Internal Counter Ends sampling and starts conversion". Scan Enable must be on.

Code is pretty straightforward after watching the debug window

    while (1)
    {       
        while(!ADC1_IsConversionComplete(POT));
        conversion = ADC1_ConversionResultGet(POT);        

        
       if (conversion >= 512)
       
       {
          OUTPUT_LED_SetHigh();
       }  
          else
          {      
          OUTPUT_LED_SetLow();    
           
       }
        // Add your application code
    }
    return 1; 

Be Sure to include %d in printf in order to display an integer


       printf("POT:= %d\r\n", conversion);
       
#define FCY 7370000UL Must be at the top in order to use built in delays such as this:
Then the following must also be included after this:

#include <libpic30.h>

#include <stdio.h>

then the delay can be used

            __delay_ms(100);
