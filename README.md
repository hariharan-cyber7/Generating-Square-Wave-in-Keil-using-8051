# Generating-Square-Wave-in-Keil-using-8051
8051 microcontroller project that generates a square wave on P1.0 using Timer0 Mode 1 in Keil µVision.

# 1.GENERATING SQUARE WAVE IN KEIL IN C


## AIM:
Write a 8051 c program to generate a square wave with frequency of 50khz

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software

## PROGRAM:
```
#include <reg51.h>

sbit sqWave = P1^0;

void main()
{
    unsigned char TH0_val = 0xFF;
    unsigned char TL0_val = 0xF6;

    TMOD = 0x01; 

    while(1)
    {
        TH0 = TH0_val;
        TL0 = TL0_val;
        TR0 = 1;          
        while(TF0 == 0);  
        TR0 = 0;          
        TF0 = 0;          
    }
}
```

### OUTPUT:
![WhatsApp Image 2025-10-18 at 16 03 58_9c40ca54](https://github.com/user-attachments/assets/af08b577-f55e-494b-ade4-d4b2c175529c)

### RESULT:
Thus the 8051 C program to generate a square wave with frequency of 50khz using keil was done and shown the output.



# 2.GENERATING SQUARE WAVE IN KEIL IN ASSEMBLY 

## AIM:
Write a 8051 program to generate a square wave with frequency of 50khz

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM:
```
CLR  P1.0          
MOV  TMOD, #01H    
AGAIN:
MOV  TL0, #0F7H  
MOV  TH0, #0FFH   
CPL  P1.0         
SETB TR0          
WAIT:
JNB  TF0, WAIT    
CLR  TR0          
CLR  TF0         
SJMP AGAIN       
END
```
### OUTPUT:
![WhatsApp Image 2025-10-18 at 16 03 16_9b38f22d](https://github.com/user-attachments/assets/8745cf3d-fff6-45bd-9548-ac774b01e1e3)

### RESULT:
Thus the 8051 prpgram to generate a square wave with the frequency of 50khz using 8051 KEIL was done and shown the output
