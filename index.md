


## Contents

 Level 1  

1. Hello World LED Blinking  
2. Traffic Light  
3. LED Chasing Effect
4. Button Controlled LED
5. Buzzer  
6. RGB LED
7. LDR Light Sensor
8. Flame Sensor
9. LM35 Temperature Sensor
10. IR Remote Control Using TSOP
11. Potentiometer analog Value Reading
12. 7 Segment Display



## Experiment 1

## HELLO WORLD LED BLINKING




### Components required

- Arduino uno*1
- LED *1
- JUMPERWIRE*2
- Breadboard*1
- 220 OHM RESISITOR*1

### Circuit diagram

![Exp1CD](content/HELLO.png?raw=true "Models")


### Code

```C

int ledPin = 1; // define digital pin 1.
void setup()
{
pinMode(ledPin, OUTPUT);// define pin with LED connected as output.
}
void loop()
{
digitalWrite(ledPin, HIGH); // set the LED on.
delay(1000); // wait for a second.
digitalWrite(ledPin, LOW); // set the LED off.
delay(1000); // wait for a second
}


```

### output


<iframe width="560" height="315" src="https://www.youtube.com/embed/NO0uF0axMNk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



## Experiment 2

## TRAFFIC LIGHT 


### Components required

- RED M5 LED*1
- YELLOW M5 LED*1
- GREEN M5 LED*1
- 220 OHM RESISITOR*3
- Breadboard*1
- JUMPERWIRE* several

### Circuit diagram

![Exp2CD](content/TRAF.png?raw=true "Models")

### Code

```c
int redled =13; // initialize digital pin 13.
int yellowled =11; // initialize digital pin 11.
int greenled =10; // initialize digital pin 10.
void setup()
{
pinMode(redled, OUTPUT);// set the pin with red LED as “output”
pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
}
void loop()
{
digitalWrite(greenled, HIGH);//// turn on green LED
delay(5000);// wait 5 seconds

digitalWrite(greenled, LOW); // turn off green LED
for(int i=0;i<3;i++)// blinks for 3 times
{
delay(500);// wait 0.5 second
digitalWrite(yellowled, HIGH);// turn on yellow LED
delay(500);// wait 0.5 second
digitalWrite(yellowled, LOW);// turn off yellow LED
} 
delay(500);// wait 0.5 second
digitalWrite(redled, HIGH);// turn on red LED
delay(5000);// wait 5 seconds
digitalWrite(redled, LOW);// turn off red LED
}
```

### output

![Exp2Out](content/TRAFFIC.mp4?raw=true "Models")

## Experiment no 3

## LED CHASING Effect


### Components required

-  LED *6
- ARDUINO BOARD*1
-  220 OHM RESISITOR*6
- Breadboard*1
- USB CABLE*1
- Breadboard*13
 

### Circuit diagram
  
![Exp3CD](content/LEDCH.png?raw=true "Models")

### code
```C
int BASE = 8 ;  // the I/O pin for the first LED
int NUM = 12;   // number of LEDs
void setup()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT);   // set I/O pins as output
   }
}
void loop()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW);    // set I/O pins as “low”, turn off LEDs one by one.
     delay(200);        // delay
   }
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH);    // set I/O pins as “high”, turn on LEDs one by one
     delay(200);        // delay
   }  
}
```
### output

![Exp3Out](content/CHASE.mp4?raw=true "Models")

### Experiment no 4

### BUTTON CONTROLL LED

### Components required

- Arduino uno*1
- button switch*1
- RED M5 LED*1
- 220 OHM RESISITOR*1
- 10 K OHM RESISITOR*1
- Breadboard*1
- JUMPERWIRE*6
- USB cable*1


### Circuit diagram

![Exp4CD](content/SWITCH.png?raw=true "Models")

### code
```c
int ledpin=13;// initialize pin 13
int inpin=10;// initialize pin 10
int val;// define val
void setup()
{
pinMode(ledpin,OUTPUT);// set LED pin as “output”
pinMode(inpin,INPUT);// set button pin as “input”
}
void loop()
{
val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
if(val==LOW)// check if the button is pressed, if yes, turn on the LED
{ digitalWrite(ledpin,LOW);}
else
{ digitalWrite(ledpin,HIGH);}
}

```

### output

![Exp4Out](content/SWBU.mp4?raw=true "Models")

### Experiment 5
### Buzzer

### Components required

 - Arduino*1
 - Breadboard*1
 - Buzzer*1
 - Jumper wire*2
 - Usb cable*1

### Circuit diagram

![Exp5CD](content/BUZ.png?raw=true "Models")



### code

```C
int buzzer=3;// initialize digital IO pin that controls the buzzer
void setup() 
{ 
  pinMode(buzzer,OUTPUT);// set pin mode as “output”
} 
void loop() 
{
digitalWrite(buzzer, HIGH); // produce sound
}
```

### output


![Exp5Out](content/BUZZER.mp4?raw=true "Models")


### Experiment  6

###  RGB LED

### Components required
 -  Arduino uno
 - usb cable
 - RGB LED
 - RESISTOR
 - JUMPER wire
 - Breadboard

 ### Circuit diagram

 
![Exp6CD](content/RGB.png?raw=true "Models")

### code

```C
int redpin = 11; //select the pin for the red LED
int bluepin =5; // select the pin for the blue LED
int greenpin =4;// select the pin for the green LED
int val;
void setup() {
  pinMode(redpin, OUTPUT);
  pinMode(bluepin, OUTPUT);
  pinMode(greenpin, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(11, val);
   analogWrite(5, 255-val);
   analogWrite(4, 128-val);
   delay(1); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(11, val);
   analogWrite(5, 255-val);
   analogWrite(4, 128-val);
   delay(1); 
  }
 Serial.println(val, DEC);
}
```
### output
![Exp6Out](content/6GB.mp4?raw=true "Models")

### Experiment 7

### LDR LIGHT Sensor

### Components required

 - Arduino uno
 - PHOTO RESISITOR*1
 - Breadboard*1
 - RED LED M5 *1
 - 10 K OHM RESISTOR *1
 - 220 OHM RESISITOR*1
 - JUMPERWIRE *5
 - USB CABLE *1

 ### Circuit diagram
 
![Exp7CD](content/LDR.png?raw=true "Models")

### code
```C
int potpin=3;// initialize analog pin 3, connected with photovaristor
int ledpin=11;// initialize digital pin 11, 
int val=0;// initialize variable val
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin 11 as “output”
Serial.begin(9600);// set baud rate at “9600”
}
void loop()
{
val=analogRead(potpin);// read the value of the sensor and assign it to val
Serial.println(val);// display the value of val
analogWrite(ledpin,val/4);// set up brightness（maximum value 255）
delay(10);// wait for 0.01 
}
```
### output


![Exp7Out](content/ NIGH.mp4?raw=true "Models")

### Experiment 8

### FLAME Sensor

### Components required

 - Arduino uno*1
 - Flame sensor*1
 - Buzzer*1
 - 10k RESISITOR*1
 - JUMPERWIRE *6
 - usb cable*1 

 ### Circuit diagram

 ![Exp8CD](content/FLAME.png?raw=true "Models")

 ### code
 ```C
 int flame=5;// select analog pin 5 for the sensor
int Beep=6;// select digital pin 6 for the buzzer
int val=0;// initialize variable
 void setup() 
{
  pinMode(Beep,OUTPUT);// set LED pin as “output”
 pinMode(flame,INPUT);// set buzzer pin as “input”
 Serial.begin(9600);// set baud rate at “9600”
 } 
void loop() 
{ 
  val=analogRead(flame);// read the analog value of the sensor 
  Serial.println(val);// output and display the analog value
  if(val>0)// when the analog value is larger than 600, the buzzer will buzz
  {  
   digitalWrite(Beep,HIGH); 
   }else 
   {  
     digitalWrite(Beep,LOW); 
    }
   delay(500); 
}
```
### output

![Exp8Out](content/FLAM.mp4?raw=true "Models")

### output

### Experiment 9

### LM35 Temperature sensor

### Components required

 - Arduino uno*1
 - JUMPERWIRE*5
 - Breadboard*1
 - USB CABLE*1
 - LM35 *1

### Circuit diagram

 ![Exp9CD](content/TEMP.png?raw=true "Models")

### code

```C
int potPin = 5; // initialize analog pin 5 for LM35 temperature sensor
void setup()
{
Serial.begin(9600);// set baud rate at”9600”
}
void loop()
{
int val;// define variable
int dat;// define variable
val=analogRead(0);// read the analog value of the sensor and assign it to val
dat=(125*val)>>8;// temperature calculation formula
Serial.print("Tep");// output and display characters beginning with Tep
Serial.print(dat);// output and display value of dat
Serial.println("C");// display “C” characters
delay(500);// wait for 0.5 second
}

```

### output


![Exp9Out](content/TEMP.mp4?raw=true "Models")

### Experiment 10


### IR REMOTE CONTROLL USING TSOP

### Components required

 - Arduino uno*1
 - JUMPERWIRE*11
 - Breadboard*1
 - Infrared Remote Controller*!
 - 220 ohm RESISITOR*6
 - usb cable*1
 - LED *6

### Circuit diagram


 ![Exp10CD](content/IRS.png?raw=true "Models")


### code
```C



```
![Exp10Out](content/3in1.jpg?raw=true "Models")



### Experiment 11

### Potentionmeter analogvalue Reading

### components required

 - Arduino uno*1
 - 10k Potentiometer*!
 - Breadboard*!
 - jumper wires*3
 - usb cable*1

### Circuit diagram
 ![Exp11CD](content/POT.png?raw=true "Models")

 ### code
 ```C 
 int potpin=1;// initialize analog pin 1
int ledpin=11;// initialize digital pin 11
int val=0;// define val, assign initial value 0
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin as “output”
Serial.begin(9600);// set baud rate at 9600
}
void loop()
{
digitalWrite(ledpin,HIGH);// turn on the LED on pin 11
delay(50);// wait for 0.05 second
digitalWrite(ledpin,LOW);// turn off the LED on pin 11
delay(50);// wait for 0.05 second
val=analogRead(potpin);// read the analog value of analog pin 1, and assign it to val 
Serial.println(val);// display val’s value
}

```

### output

![Exp11Out](content/POTENT.mp4?raw=true "Models")


### Experiment 12

### 7 SEGMENT DISPLAY

### components required

 - Arduino uno
 
 - 1-digit LED segment display*1
 - 220 ohm RESISITOR*8
 - Breadboard*1
 - JUMPERWIRE* several
 - usb cable*1

### Circuit diagram

![Exp12CD](content/DISP.png?raw=true "Models")

### code

```C
int a=7;// set digital pin 7 for segment a
int b=6;// set digital pin 6 for segment b
int c=4;// set digital pin 4 for segment c
int d=10;// set digital pin 10 for segment d
int e=11;// set digital pin 11 for segment e
int f=12;// set digital pin 12 for segment f
int g=13;// set digital pin 13 for segment g
int dp=3;// set digital pin 3 for segment dp
void digital_0(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_1(void) // display number 1
{
unsigned char j;
digitalWrite(c,HIGH);// set level as “high” for pin 5, turn on segment c
digitalWrite(b,HIGH);// turn on segment b
for(j=7;j<=11;j++)// turn off other segments
digitalWrite(j,LOW);
digitalWrite(dp,LOW);// turn off segment dp
}
void digital_2(void) // display number 2
{
unsigned char j;
digitalWrite(b,HIGH);
digitalWrite(a,HIGH);
for(j=9;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
digitalWrite(c,LOW);
digitalWrite(f,LOW);
}
void digital_3(void) // display number 3
{digitalWrite(g,HIGH);
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(dp,LOW);
digitalWrite(f,LOW);
digitalWrite(e,LOW);
}
void digital_4(void) // display number 4
{digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
digitalWrite(a,LOW);
digitalWrite(e,LOW);
digitalWrite(d,LOW);
}
void digital_5(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b, LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_6(void) // display number 6
{
unsigned char j;
for(j=7;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(c,HIGH);
digitalWrite(dp,LOW);
digitalWrite(b,LOW);
}
void digital_7(void) // display number 7
{
unsigned char j;
for(j=5;j<=7;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
for(j=8;j<=11;j++)
digitalWrite(j,LOW);
}
void digital_8(void) // display number 8
{
unsigned char j;
for(j=5;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void setup()
{
int i;// set variable
for(i=4;i<=11;i++)
pinMode(i,OUTPUT);// set pin 4-11as “output”
}
void loop()
{
while(1)
{
digital_0();// display number 0
delay(1000);// wait for 1s
digital_1();// display number 1
delay(1000);// wait for 1s
digital_2();// display number 2
delay(1000); // wait for 1s
digital_3();// display number 3
delay(1000); // wait for 1s
digital_4();// display number 4
delay(1000); // wait for 1s
digital_5();// display number 5
delay(1000); // wait for 1s
digital_6();// display number 6
delay(1000); // wait for 1s
digital_7();// display number 7
delay(1000); // wait for 1s
digital_8();// display number 8
delay(1000); // wait for 1s
digital_9();// display number 9
delay(1000); // wait for 1s
}}

```

### output


![Exp11Out](content/PLAYD.mp4?raw=true "Models")




