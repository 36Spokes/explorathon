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

 if you want to use that.
## Step 3: Configure Your Hardware
Once you have all your parts together, you're ready to design This simply means: "Where do I plug the wires?"
