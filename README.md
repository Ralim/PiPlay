# PiPlay
A raspberry Pi zero powered mp3 player project.

Exploring the idea of using the Raspberry Pi Zero to create fairly portable MP3 player built in the style of the iPod classic - Lots of storage.


The design is based around adding multiple HAT's to the Raspberry Pi Zero.
The unit will have a base PCB which will be larger than the pi, this houses the screen, user input, and power management.

Stacked ontop of the base PCB will be the raspberry pi, and the two extra 'HATs' for the PI. Note that officially you cannot stack HATs, however each of these boards are designed to be useable individually as well. Thus they are 'HATs', but not used as 'HATs' in this case (neither will have EEPROM populated).

The idea behind this system is that it will seperate out all the functionality into smaller reusable boards.


## Audio Dac HAT
 
 This board impliments a shrunk design similar to the DAC+ pro board for the full size pi. While this means that some signals are a little bit too close to the audio path for my liking, this is a fairly small board. A small 25mW headphone amplifier is used in this design as I have that ic on hand from a previous project. Once the board arrives this will be tested if it is loud enough, if not it will be replaced by a more powerful headphone amp.

 This design uses the dual oscillators to provide low jitter audio playback for both 44 and 48Khz related frequencies.

 ## Triple SD Hat

 This HAT abuses the pi to mount an extra 3 SD cards without using the USB port.
 One card is mounted over the fast SDIO bus, so this card is exposed out the side of the unit, as this card can be removed as a way to provide removable storage like most MP3 players.
 Two internal cards are mounted over the SPI bus, while this method works okay, it is rather slow compared to the SDIO method. This is perfectly acceptable for playback of MP3 files as we do not need high speeds.
