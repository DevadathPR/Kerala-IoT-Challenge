


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

<iframe width="560" height="315" src="https://www.youtube.com/embed/vibTpPs5KSY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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

<iframe width="560" height="315" src="https://www.youtube.com/embed/pneRVem7jHQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment no 4

## BUTTON CONTROLL LED

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

<iframe width="560" height="315" src="https://www.youtube.com/embed/jcgHOgFfgmc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment 5
## Buzzer

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


<iframe width="560" height="315" src="https://www.youtube.com/embed/xF5hfGGBwbA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment  6

##  RGB LED

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
<iframe width="560" height="315" src="https://www.youtube.com/embed/uxBNo-lSBf4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment 7

## LDR LIGHT Sensor

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


<iframe width="560" height="315" src="https://www.youtube.com/embed/23LN822j36s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment 8

## FLAME Sensor

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

<iframe width="560" height="315" src="https://www.youtube.com/embed/j2_msI2iJns" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### output

## Experiment 9

## LM35 Temperature sensor

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


<iframe width="560" height="315" src="https://www.youtube.com/embed/XVpzWmQa46I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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


 ![Exp10CD](content/IRSD.png?raw=true "Models")


### code
```C
#include <IRremote.h>
int RECV_PIN = 8;
int LED1 = 2;
int LED2 = 3;
int LED3 = 4;
int LED4 = 5;
int LED5 = 6;
int LED6 = 7;
long on1  = 14498;
long off1 = 14500;
long on2 = 10407;
long off2 = 14504;
long on3 = 10411;
long off3 = 14509;
long on4 = 10414;
long off4 = 14481;
long on5 = 10386;
long off5 = 0x00FF42BD;
long on6 = 0x00FF4AB5;
long off6 = 0x00FF52AD;
IRrecv irrecv(RECV_PIN);
decode_results results;

void setup()
 {
  pinMode(RECV_PIN, INPUT);   
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
  pinMode(LED4, OUTPUT);
  pinMode(LED5, OUTPUT);
  pinMode(LED6, OUTPUT);  
  pinMode(13, OUTPUT);
  Serial.begin(9600);
   irrecv.enableIRIn(); // Start the receiver
 }
int on = 0;
unsigned long last = millis();
void loop() 
{
  if (irrecv.decode(&results)) 
   {
    Serial.println(results.value);
    
    if (results.value == on1 )
       digitalWrite(LED1, HIGH);
    if (results.value == off1 )
       digitalWrite(LED1, LOW); 
    if (results.value == on2 )
       digitalWrite(LED2, HIGH);
    if (results.value == off2 )
       digitalWrite(LED2, LOW); 
    if (results.value == on3 )
       digitalWrite(LED3, HIGH);
    if (results.value == off3 )
       digitalWrite(LED3, LOW);
    if (results.value == on4 )
       digitalWrite(LED4, HIGH);
    if (results.value == off4 )
       digitalWrite(LED4, LOW); 
    if (results.value == on5 )
       digitalWrite(LED5, HIGH);
    if (results.value == off5 )
       digitalWrite(LED5, LOW); 
    if (results.value == on6 )
       digitalWrite(LED6, HIGH);
    if (results.value == off6 )
       digitalWrite(LED6, LOW);        
    last = millis();      
irrecv.resume(); // Receive the next value
  }
}
```
<iframe width="560" height="315" src="https://www.youtube.com/embed/NNPvRUwSq5s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Experiment 11

## Potentionmeter analogvalue Reading

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

<iframe width="560" height="315" src="https://www.youtube.com/embed/WQCxHPlNask" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Experiment 12

## 7 SEGMENT DISPLAY

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


![image](https://user-images.githubusercontent.com/51152887/151688624-75e706e9-4ae7-4f9a-9af8-a629ab119c5c.png)


## Activity 1

## Automatic night lamp using LDR

### components required

 - Arduino uno*1
 - LDR*1
 - Breadboard*!
 - jumper wires
 - usb cable*1
 - LED*1

### Circuit diagram
 ![image](https://user-images.githubusercontent.com/51152887/151689148-12f31077-211e-466c-b38d-20ae948de59a.png)

### code

```C 
int ldr=A0;//Set A0(Analog Input) for LDR.
int value=0;
void setup() {
Serial.begin(9600);
pinMode(3,OUTPUT);
}

void loop() {
value=analogRead(ldr);//Reads the Value of LDR(light).
Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.
Serial.println(value);
if(value<20)
  {
    digitalWrite(3,HIGH);//Makes the LED glow in Dark.
  }
  else
  {
    digitalWrite(3,LOW);//Turns the LED OFF in Light.
  }
}
```

### output

<iframe width="560" height="315" src="https://www.youtube.com/embed/F1Q8d6cogkU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Activity 2

## Digital dice

### components required

 - Arduino uno*1
 - 7 segment diplay*1
 - Breadboard*!
 - jumper wires
 - usb cable*1
 - push button*1
 - 330 ohm resistors*8
 - 10k ohm resistors*1

### Circuit diagram
![image](https://user-images.githubusercontent.com/51152887/151689314-dd85afec-b75c-4cbf-8847-14020d4fc522.png)

### code

```C 
int a=4;// set digital pin 7 for segment a
int b=3;// set digital pin 6 for segment b
int c=5;// set digital pin 4 for segment c
int d=8;// set digital pin 10 for segment d
int e=7;// set digital pin 11 for segment e
int f=9;// set digital pin 12 for segment f
int g=10;// set digital pin 13 for segment g
int dp=6;// set digital pin 3 for segment dp
int randnum = 0;

void digital_0(void) // display number 0
{

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
digitalWrite(a,LOW);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,LOW);
digitalWrite(e,LOW);
digitalWrite(f,LOW);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}

void digital_2(void) // display number 2
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,LOW);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,LOW);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
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
digitalWrite(a,HIGH);
digitalWrite(b,LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_7(void) // display number 7
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,LOW);
digitalWrite(e,LOW);
digitalWrite(f,LOW);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_8(void) // display number 8
{


digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) // display number 9
{

digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d, LOW);
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
pinMode(2, INPUT);
}
void loop()
{
  while(1)
  {
  if (digitalRead(2)== HIGH)
  {
    delay(100);
    randnum = random(6);
    
    if (randnum == 1)
      {digital_1();}// display number 1
    

    else if (randnum == 2)
      {digital_2();}// display number 2
    

    else if (randnum == 3)
      digital_3();// display number 3
    

    else if (randnum == 4)
      digital_4();// display number 4
    

    else if (randnum == 5)
      digital_5();// display number 5
    

    else if (randnum == 6)
     {digital_6();}// display number 6
    
  }
}
}
```

### output

<iframe width="560" height="315" src="https://www.youtube.com/embed/dejaennQURA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

