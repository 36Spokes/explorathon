# Making a Paper Piano
This page describes all the details of how to make your own paper piano using electrically conductive ink and an Arduino Uno microcontroller platform.  The project offers a great introduction to some simple coding, bringing engineering and art together to create something amazing!  We hope you enjoy completing this project!
## The Theory: What, Why, How
### What is this project all about?
Low cost sensors have already changed our world.  For example, smart phones are packed full of touch sensors, light sensors, movement sensors and temperature sensors, to name a few.  What if we could use sensors to detect infectious diseases really quickly with something like a mobile phone?  Or measure the quality of drinking water, or soil fertility rapidly?  Currently, most of these challenges require a laboratory with a trained scientist who knows what they are doing.  In this research, we’re borrowing techniques from Art and Design to make sensors that are low cost without the need for a specialist laboratory.
### Why print piano keyboards using woodblocks?
Printing is used everywhere to make multiple copies of the same design.  Woodblock printing is one of the oldest printing methods.  We are using it here because it is highly accessible: at its simplest nothing more than a piece of wood and a sharp tool are needed to create a pattern that can then be printed hundreds of times over. In our research, we’re borrowing these techniques and combining them with electronic inks to make functioning sensors.  The example here shows how woodblock printing can be used to make a sensors similar to the touch screen on your phone.
### How does it work?
The keys of the piano are printed with a carbon based ink.  Many carbon materials are conductive and we can use electronic circuits to measure changes in their electrical properties. When you touch the keys of the piano, your body has an effects on the charge (electrons) present within the circuit. This is an example of a capacitive sensor.
![capactive sensor](https://user-images.githubusercontent.com/54633461/201306290-296907a6-4227-48fa-8902-9b04b5fa294c.png)

# Getting Started
## Step 1: Get the Parts You Need
The electrical components required for this project can be purchase from online electronics suppliers. For example, RS Online, Digikey, Mouser, Farnell etc.To complete this project, you need the following items:
- An [Arduino Uno](https://store.arduino.cc/products/arduino-uno-rev3)
- 7 off 10 MOhm resistors
- [Jumper wires with solid tips](https://en.wikipedia.org/wiki/Jump_wire)
- [A small solderless breadboard](https://en.wikipedia.org/wiki/Breadboard)
- [A speaker, with presoldered wires](https://en.wikipedia.org/wiki/Electrodynamic_speaker_driver). Generally referred simply as a speaker. For this project, a speaker with a power of maximum 0.5 Watts and an 8 Ohm impedance is required.
- Conductive electrical paint. For our project, we used [Bare Conductive Electrical Paint](https://www.bareconductive.com/collections/electric-paint)
- A method to print onto paper or another type of substrate.  For our project, we wanted to demostrate the use of woodblock printing, but you could also use a paintbrush to create the piano keys, or any other type of capactive touch sensor!
- Paper clips to connect the sensor to the Arduino
- A computer with the free [Arduino Software Installed](https://www.arduino.cc/en/software) (called an Integrated Development Environment or IDE for short) and a USB A cable to be able to programme the Arduino.
## Step 2: Design and Make Your Keyboard
We designed a woodblock print for our keyboard to show how many copies of the same design can be made. You don't need to be a fancy as this - simply painting a keyboard onto a piece of paper with the conductive paint described in step 1 will also work well.  Our keyboard design file is included here as [SVG file]!(https://user-images.githubusercontent.com/54633461/201313281-0c1749cc-5637-45b9-a207-44c5668a9cd5.svg) and as a [pdf file][Printed Piano not flipped.pdf](https://github.com/36Spokes/explorathon/files/9989064/Printed.Piano.not.flipped.pdf). You can simply print these off and then paint over the black bits - be sure to keep the keys seperate though! If you want to try [relief (or block) printng](https://www.royalacademy.org.uk/article/family-how-to-relief-printing#:~:text=What%20is%20a%20relief%20print,show%20up%20on%20your%20paper.) your piano, remember that you need to flip the image first.

## Step 3: Configure Your Hardware
Once you have all your parts together, you're ready to design This simply means: "Where do I plug the wires?".  You can follow the breadboard design below. 
![circuit layout](https://user-images.githubusercontent.com/54633461/201464756-816bb90c-4622-45f6-a2e9-c02d8315108a.png)

The circuit is very simple and involes placing the 1 MOhm resistors between pin 2 (used to power the sensor) and a sensing pin.  Repeat this for each of the seven notes.  The other end of the wires connect to the piano.  You can do this using paperclips by pushing one end of the clip into a jumper cable with a plug like end and the other end into the breadboard as shown above.

![1668240174905](https://user-images.githubusercontent.com/54633461/201464872-ac8f99f1-0568-4da6-98fb-5fc9e2056655.jpeg)

The final step is adding the speaker to the circuit.  To do this, simply connect the red wire from the speaker to pin 11 on the breadboard and the black wire to ground.  This produces a tone using something called [Pulse Width Modulation](https://en.wikipedia.org/wiki/Pulse-width_modulation) and it doesn't produce a very nice sound. As you learn more, you can improve this by adding an audio shield, or creating your own digital to analog circuit.

![1668240466698](https://user-images.githubusercontent.com/54633461/201464994-be70eb55-7c96-4fbc-af60-32cac6015390.jpeg)

## Step 4: Upload the code to the Aruidno
We adapted this code from a piano project by Barqunics, avialbe on the Arduino Playground [here](https://create.arduino.cc/projecthub/Barqunics/paper-piano-with-arduino-e27da7?ref=tag&ref_id=piano&offset=1).  Open up the Arduino IDE, create a new sketch and copy and paste this code into it (you can lean how to use the IDE [here](https://docs.arduino.cc/software/ide-v2/tutorials/getting-started-ide-v2):

```

/* Original project by Oh Hai Seng 07 November 2013 
 To watch the Demo of his Project:
     http://www.youtube.com/watch?v=X4QNT5hOHLs&list=TLlm-tAV1gEzDF4VV39VdjCSLNlfe0tTpU

Adapted by Andrew Ward 10 November 2022 for Explorathon 2022, Glasgow UK
    https://github.com/36Spokes/explorathon

*/    

// Import the CapacitiveSensor Library.
#include <CapacitiveSensor.h>

// Define the pin out for the speaker.
#define speaker 11


// Set the Send Pin & Receive Pin.
CapacitiveSensor   cs_2_3 = CapacitiveSensor(2,3);        
CapacitiveSensor   cs_2_4 = CapacitiveSensor(2,4);         
CapacitiveSensor   cs_2_5 = CapacitiveSensor(2,5);     
CapacitiveSensor   cs_2_6 = CapacitiveSensor(2,6);     
CapacitiveSensor   cs_2_7 = CapacitiveSensor(2,7);      
CapacitiveSensor   cs_2_8 = CapacitiveSensor(2,8);         
CapacitiveSensor   cs_2_9 = CapacitiveSensor(2,9);    


void setup()                    
{
  //cs_2_6.set_CS_AutocaL_Millis(0xFFFFFFFF);     // turn off autocalibrate on channel 1 - just as an example
  
  // Arduino start communicate with computer.
 Serial.begin(9600);  //Remove this line if you don't want to power the piano from a PC.
}

void loop()                    
{
  // Set a timer.
  long start = millis();
  
  // Set the sampling rate of the sensors.
  long noteC =  cs_2_3.capacitiveSensor(3000);
  long noteD =  cs_2_4.capacitiveSensor(3000);
  long noteE =  cs_2_5.capacitiveSensor(3000);
  long noteF =  cs_2_6.capacitiveSensor(3000);
  long noteG =  cs_2_7.capacitiveSensor(3000);
  long noteA =  cs_2_8.capacitiveSensor(3000);
  long noteB =  cs_2_9.capacitiveSensor(3000);
  

/*Uncomment this section if you need to debug the programme 
 Serial.print(millis() - start);        // check on performance in milliseconds
 Serial.print("\t");                    // tab character for debug windown spacing
*/

// Remove the next 13 lines if you don't want to view the data on a PC.
  Serial.print(noteC);                  // print sensor output 1
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.print(noteD);                  // print sensor output 2
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.print(noteE);                  // print sensor output 3
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.print(noteF);                  // print sensor output 4
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.print(noteG);                  // print sensor output 5
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.print(noteA);                  // print sensor output 6
  Serial.print("\t");                    // Leave some space before print the next output
  Serial.println(noteB);                   // print sensor output 7

    
  // When hand is touched the sensor, the speaker will produce a tone.
  // I set a threshold for it, so that the sensor won't be too sensitive.
  if (noteC > 1000) tone(speaker,261);   // frequency
  if (noteD > 1000) tone(speaker,293);   // you can see https://www.arduino.cc/en/Tutorial/toneMelody if you want to change frequency
  if (noteE > 1000) tone(speaker,329);
  if (noteF > 1000) tone(speaker,349);
  if (noteG > 1000) tone(speaker,392);
  if (noteA > 1000) tone(speaker,440);
  if (noteB > 1000) tone(speaker,493);
  
  // When hand didn't touch on it, no tone is produced.
  if (noteC<=500  &  noteD<=500  &  noteE<=500 & noteF<=500  &  noteG<=500  &  noteA<=500 &  noteB<=500)
    noTone(speaker);

  delay(10);                             // arbitrary delay to limit data to serial port 
}

```

You also need to add the capacitiveSensor library to the Sketch too.  You can find out how to add lbraries to sketechs by clicking on the library manager (on the left hand side of the IDE and searching for the capacitiveSensor library.  Once this is done, you can verfiy and upload your sketch.

**Happy Coding!**
