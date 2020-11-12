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
