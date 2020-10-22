Project 3 involves turning on an LED depending on what value the ADC reads. Code is pretty simple

#include "mcc_generated_files/system.h"
#include "mcc_generated_files/mcc.h"    //NOTE HAD TO ADD THIS.
/*
                         Main application
 */
int main(void)
{
    // initialize the device
    SYSTEM_Initialize();
        int conversion;
        ADC1_Initialize();
        ADC1_Enable();

        //Provide Delay

    
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
}
    
    
   ![ADC Settings](https://raw.githubusercontent.com/chrissavage2300/PIC33EP-Tutorial/main/Project%203/ADC%20Settings.png)
