---
title: "Project VOID - Animatronic Using OpenAI's Real-Time API"
date: 2025-04-25
---

<img src="https://github.com/user-attachments/assets/489e931a-d1e8-4cd4-835f-132ac85c77f7" alt="project" width="300"/>

Teddy Ruxpin was a popular animatronic toy in the 1980's. The original model used a metal cassette player on the back of the toy, where the toy would then talk. The purpose of this project was to rewire the innerworkings of the toy so it could have an actual, real conversation with the user. VOID stands for Voice Operated Intelligent Device, and I wanted to use OpenAI's new Real-Time API to bring new life into this animatronic.

<img src="https://github.com/user-attachments/assets/8a83c0b0-6ac4-40c7-9f59-95118bc5dc50" alt="takingitapart" width="300"/>

First, I opened the back of the toy and disconnected the wires connecting to the head, cassette player, and batteries. Most of the board was not needed for this project, as a majority of it would be replaced by an Arduino Uno and a Raspberry PI.


<img src="https://github.com/user-attachments/assets/01e91991-8dc2-4432-b1a7-51db9b06a749" alt="thehead" width="300"/>

The first model of the Teddy Ruxpin used 3 motors, one for the eyes, nose, and mouth. I decided to replace these with new, more modern servomechanisms that could easily be used with the Arduino Uno. To do this, I slid out the original motors and used a rotary tool to cut them into shapes that the new servos would fit into. 

<img src="https://github.com/user-attachments/assets/5009c4fc-2855-4597-8e3a-791b3436240f" alt="servos" width="300"/>

The original motors used a series of gears to move the individual parts of the face. I removed them and carefully attached the servo with hot glue to hold it into position. I repeated this for each of the three motors. After sliding the servos back in, I tested it using a breadboard and the Arduino. It worked nearly perfectly. 

<img src="https://github.com/user-attachments/assets/1a432d2c-a04f-461a-84f5-5a177751b841" alt="code" width="300"/>

<img src="https://github.com/user-attachments/assets/d7cb056d-52d9-419c-843b-d8f6b0cc6d7b" alt="code" width="300"/>

The idea to get this to work was simple. The Raspberry PI would recieve audio input from a USB Microphone, OpenAI's Real-Time API would recieve the response, then send an audio response back. Using an audio splitter, the speaker would play the audio response and the Arduino would read the analog input, then turn it into digitial output that the servos would understand and respond to. However, I had never worked with OpenAI's API's before, and it was much more difficult then I originally expected. The Real-Time API's documentation was outdated, and it took several days of research to get ChatGPT to respond. However, in the end after much troubleshooting, I was able to get the Python script to run. 


<img src="https://github.com/user-attachments/assets/fb96437f-ce9a-4dd2-8550-ceb7ebd71a0f" alt="desolder" width="300"/>

The original speaker's amplification was built into the board, and the speaker itself would not output loud enough. After a few days of research, I decided to solder off the original LM1086 chip that was on the original board and build my own amplification circuit with a volume control. I had never done this before, and this was one of the hardest parts of the project. I used desoldering wick and carefully removed the chip from the board. 

<img src="https://github.com/user-attachments/assets/a272ae1b-a945-4c1d-a8b4-ab2a6f985452" alt="breadboard" width="300"/>

From a schematic I found in "Practical Electronics for Inventors, 4th Edition", I breadboarded a simple audio amplifer circuit and used a 10K potientmeter as a volume control. I stripped the wires from an old aux cord and tinned the wires to use as the plug in for my new amplifer speaker combination. Although noisy at first, I assumed that soldering the parts onto the protoboard would resolve those issues. 

<img src="https://github.com/user-attachments/assets/655d5193-a62d-4716-aa0c-45cc50c10e7d" alt="finaltouches" width="300"/>

To completely remove the project from breadboards, I carefully soldered together the amplifer and used the remaining space to solder on the positive and ground cables from the servos. Then, I soldered header pins to some black and red wire to plug into the Arduino. 


<img src="https://github.com/user-attachments/assets/7729c25f-fb88-4d92-baa9-829b8382a0a8" alt="finaltouches" width="300"/>

For the Arduino to recieve audio input, I soldered wire to a male 3.5mm Aux connector and plugged it into an analog pin and ground. Then, the signal pins from the servos were plugged into the digital pins of the Arduino, powered by the 5 Volt pin, and 3.3 Volt pin was used for the amplifer. At first, I was nervous that the Arduino would not be able to power the amplifer and servos together, but testing proved it worked perfectly. I connected the Rasbperry PI and the Arduino to two 5V battery packs, and the project was a success.


IMPROVEMENTS AND NOTES:
Project VOID was a fun dive into robotics. I learned how to convert analog signals into digital outputs, and built my first amplifer circuit. Learning how OpenAI's API's work was a valuable experience that I will definitely use for future projects as well.

There are several aspects of this project that I could most definitely improve. First would be wiring the battery packs so that instead of running on two, the Raspberry PI and Arduino could run on one. Future improvements also include adding an On/Off switch, and creating a body to place the hardware components inside of. 





