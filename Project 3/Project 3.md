Project 3 involves turning on an LED depending on what value the ADC reads. Code is pretty simple

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
    
    
   ![ADC Settings](https://raw.githubusercontent.com/chrissavage2300/PIC33EP-Tutorial/main/Project%203/ADC%20Settings.png)
