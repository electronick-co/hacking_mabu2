# hacking_mabu2
Mabu2 is a health companion bot. The idea is to control the head movements (animatronics) part of Mabu

# Serial parameters:

Baudrate: 57600


# Command decode

Header: fa 00

# List of commands:

## Power on

fa 00 02 4f 7f 0b cb

## Power off

fa 00 02 4f 8b 4c

## Version ID

fa 00 01 56 44 52

Tablet reports: MCB is running firmware version: [2.390000]

## Calibration values

fa 00 01 42 30 3e

Returns values in the tablet. 
todo: check those values

## Read VR values

fa 00 01 40 2e 3c

tablet returns status (position mabye?) of all 7 motors

## Read PID Values

fa 00 01 47 35 43

tablet returns pid 

## Reset PID values

#todo

## Slow blink

fa 00 0f 01 60 84 16 16 14 fc fc 3c 0b 0b 3c 16 16 0a bf ee

## Single cicle test
(moves eyes up and down)

fa 00 07 01 08 04 e5 7f 19 7f 19 0d

## Double cycle test
(moves eyes up and down 5 times)

fa 00 0b 01 08 08 e5 7f 19 7f e5 7f 19 7f 69 13

## 5 cycle test
(moves eyes up and down 5 times)

fa 00 17 01 08 14 e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f ab 25

## CAL LDL
Calibration of left eyelid

 fa 00 02 43 40 b3 80

 ## CAL LDR
 Calibration of right eyelid

 fa 00 02 43 20 93 60

 ## CAL ELR:
 Calibration of horizontal eye movements

 fa 00 02 43 10 83 50

 ## CAL EUD
 Calibration of vertical eye movement

fa 00 02 43 08 7b 48

## CAL NE
Calibration of vertical head movement

fa 00 02 43 04 77 44

## CAL NR
Calibration of horizontal head movement

fa 00 02 43 02 75 42

## CAL NT
Calibration of head tilt

fa 00 02 43 01 74 41

# Movement test

## LDL Left eyelid

Scroll right (eyelid close)
fa 00 04 01 40 01 ff b7 41

Scroll left (eyelid open)
fa 00 04 01 40 01 00 b7 41

## LDR Right eyelid

Scroll right (eyelid close)
fa 00 04 01 20 01 ff 57 21

Scroll left (eyelid open)
fa 00 04 01 20 01 00 57 21

## ELR Horizontal eye movement

scroll right (eyes to the right)
fa 00 04 01 10 01 ff 27 11

scroll left (eyes to the left)
fa 00 04 01 10 01 00 27 11

## EUD Vertical eye movement

scroll right (eyes looking down)
fa 00 04 01 08 01 ff 0f 09

scroll left (eyes looking up)
fa 00 04 01 08 01 00 0f 09

## NE Vertical head movement

scroll right (head up)
fa 00 04 01 04 01 ff 03 05

scroll left (head down)
fa 00 04 01 04 01 00 03 05

## NR Horizontal head movement

scroll right (head moves to the left)
fa 00 04 01 02 01 ff fc 03

scroll left (head moves to the right)
fa 00 04 01 02 01 00 fc 03

## NT Head tilt

scroll right (head tilts to the left)
fa 00 04 01 01 01 ff f9 02

scroll left (head tilts to the right)
fa 00 04 01 01 01 00 f9 02
