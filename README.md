# Square-Wave-Generation-Using-8051

## Aim:
To generate a square wave using the 8051 microcontroller and observe the waveform using Keil software and Proteus simulation.

## Apparatus Required:
•	Laptop with Keil uVision software
•	Proteus Design Suite

## Circuit Diagram Setup in Proteus:
1.	Open Proteus and create a new project.
2.	Add the following components from the library:
o	8051 Microcontroller (AT89C51)
o	Oscilloscope (to observe the waveform)
o	Resistor (1kΩ) (if using hardware)
3.	Connect P1.0 of the microcontroller to the oscilloscope's input.
4.	Save the design and proceed to programming in Keil.

## Algorithm:
1.	Configure P1.0 as an output port.
2.	Set P1.0 HIGH to generate a HIGH pulse.
3.	Introduce a delay.
4.	Set P1.0 LOW to generate a LOW pulse.
5.	Introduce a delay.
6.	Repeat the process continuously.
   
## Simulation in Proteus:
1.	Open Proteus and load the HEX file generated from Keil.
2.	Connect P1.0 to an oscilloscope.
3.	Run the simulation and observe the square wave on the oscilloscope.
4.	Adjust delay loops if needed to modify the wave frequency.


## Program:

#include<reg51.h>
sbit wave=P1^0;
void delay();
void main()
{
	wave=0;
	while(1)
	{
		wave=1;
		delay();
		wave=0;
		delay();
	}
}
void delay()
{
unsigned char i;
TMOD=0X10;
for(i=0;i<14;i++)
	{
		TH1=0X00;
		TL1=0X00;
		TR1=1;
		while(TF1==0);
		TF1=0;
	}
}

## Output:

<img width="1919" height="904" alt="ss 2" src="https://github.com/user-attachments/assets/65f1c8bb-fc92-4ab8-9069-fb689bc24c05" />

## Result:
The square wave generation using the 8051 microcontroller has been successfully implemented and simulated using Keil and Proteus.


