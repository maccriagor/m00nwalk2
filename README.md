# Challenge Name: m00nwalk2
**Category:** Forensics  
**Platform:** picoCTF 2019  
**Points:** no info.

## Description
Revisit the last transmission. We think this transmission contains a hidden message. There are also some clues : Clue 1, Clue 2, Clue 3.
Link to transmission : https://challenge-files.picoctf.net/c_fickle_tempest/43e77de115ba9b931f7e1c33b128045d7754eb3c999f81693f185be52ccf6dc9/message.wav.

Link to Clue 1 : https://challenge-files.picoctf.net/c_fickle_tempest/43e77de115ba9b931f7e1c33b128045d7754eb3c999f81693f185be52ccf6dc9/clue1.wav .

Link to Clue 2 : https://challenge-files.picoctf.net/c_fickle_tempest/43e77de115ba9b931f7e1c33b128045d7754eb3c999f81693f185be52ccf6dc9/clue2.wav .

Link to Clue 3 : https://challenge-files.picoctf.net/c_fickle_tempest/43e77de115ba9b931f7e1c33b128045d7754eb3c999f81693f185be52ccf6dc9/clue3.wav .
## Challenge Hints
Use the clues to extract the another flag from the .wav file.
## Personal Hints
1. You only need to care about decoding Clue 1 and Clue 3 on RX-SSTV , the rest can be ignored or only matter when we are on different tool.
2. RX-SSTV should automatically pick the right RX option for you right after you play an audio file.
## Analysis
- The challenge gives 4 files total which include the following content :
  1. Transmission :
  ![Alt Text](https://ibb.co/SX7TtxC0)
  3. Clue 1 :
  ![Alt Text](https://ibb.co/Xr8tgJ97)
  5. Clue 2 :
  ![Alt Text](https://ibb.co/S7RrBd5P)
  7. Clue 3 :
  ![Alt Text](https://ibb.co/Ndg7vsmZ)

## Solution
Step-by-step explanation:

Download the following tool for solving ( RX-SSTV ) : https://www.qsl.net/on6mu/rxsstv.htm.

Download the following tool to support the solving tool ( Virtual Audio Cable ) : https://vac.muzychenko.net/en/

Visit ALan Eliasen the future boy steganography tool : https://futureboy.us/stegano/

1. Select your device sound output ( right side of the volume bar ) to Line 1 which is the Virtual Audio Cable.
2. In RX-SSTV , pick setup -> Sound Control and Devices -> Pick line 1.

* This setting help the RX-SSTV to listen to your .wav file so it can decode the image, remember to switch the device sound output back after finishing with decoding.
  
3. Play each of the .wav files ( you only really need to play the clue files, the transmission file doesnt how any meaningful clue for RX-SSTV decoding progress unless you are on m00nwalk 1 ).
   
* So i was solving this in my college library and i realized that in a loud area, the RX-SSTV ( despite being on audio cable ) would make the would-be-correct decoded image quite blurry. ( This should be what the Clue 2 image mean )

4. Clue 1 should give you a password ( hidden_stegosaurus ) and Clue 3 would give you the following text "ALan Eliasen the future boy" which if you google it, click the first link and you will see a list of tools, pick steganography.

* Before we move to the fifth step, reminder to pick decode mode when you are on future boy site. ( Dont be like me and get stuck for 30 minutes because i didnt realize i was on encode mode )

5. Choose the Transmission .wav file and enter the password given in Clue 1 ( hidden_stegosaurus ) , pick View raw output as MIME-type (text/plain).
## Result
The flag for this challenge is picoCTF{the_answer_lies_hidden_in_plain_sight}. 
