# hacking_mabu2
Mabu2 is a health companion bot. The idea is to control the head movements (animatronics) part of Mabu

# Serial parameters:

Baudrate: 57600


# Command decode

Header: fa 00

# List of commands:

## Power on

fa 00 02 4f 7f 0b cb

r: fa 00 02 4f 7f 0b cb

## Power off

fa 00 02 4f 8b 4c

r: fa 00 02 4f 00 8b 4c

## Version ID

fa 00 01 56 44 52

r: fa 00 05 56 40 18 f5 c3 9e 68

Tablet reports: MCB is running firmware version: [2.390000]

## Calibration values

fa 00 01 42 30 3e

r: fa 00 2b 42 3e 05 9b 0c 5d 07 16 05 88 0c 72 07 00 08 e4 08 e4 00 5f 03 de 04 7f 01 57 0a 1e 0d c7 02 d5 00 b9 0f e4 0e 6a 0a 2c 0d c2 02 fa da 41 80 00 00 3f 80 00 00 3a a3 d7 0a 3c 03 12 6f 3e 99 99 9a 3a 83 12 6f 3d a3 d7 0a 3f 00 00 00 3a 83 12 6f 3d a3 d7 0a ce 9b

## Read VR values

fa 00 01 40 2e 3c

tablet returns status (position mabye?) of all 7 motors

Several reads to decode later:
fa 00 09 01 00 2c 5f 0a 44 5e c1 59 d3 58
fa 00 09 01 00 2c 5f 0a 44 5e c1 59 d3 58
fa 00 09 01 00 2c 5f 08 45 5e c1 59 cd 57
fa 00 09 01 00 2c 5f 08 44 5e c1 59 c9 56
fa 00 09 01 00 2c 5f 0a 44 5d c1 59 d0 57
fa 00 09 01 00 2c 5f 0a 44 5d c1 59 d0 57
fa 00 09 01 00 2c 5f 08 44 5e c1 59 c9 56
(changed position of motors)
fa 00 09 01 00 02 02 08 00 03 00 06 78 1a


All left
Command: fa 00 09 01 00 01 01 06 02 05 00 0f 78 23
Command: fa 00 09 01 00 01 01 06 02 05 00 0f 78 23
Command: fa 00 09 01 00 01 01 07 02 05 00 0f 7d 24
Command: fa 00 09 01 00 01 01 06 02 05 00 0f 78 23
Command: fa 00 09 01 00 01 01 07 02 06 00 0f 80 25
Command: fa 00 09 01 00 01 01 06 02 05 00 0f 78 23

LDL 25%
Command: fa 00 09 01 00 40 01 07 02 05 00 10 39 64
Command: fa 00 09 01 00 40 01 06 02 05 00 0f 33 62
Command: fa 00 09 01 00 40 01 07 03 05 00 0f 3c 64
Command: fa 00 09 01 00 40 01 06 02 05 00 0f 33 62
Command: fa 00 09 01 00 40 01 06 03 05 00 0f 37 63

LDL50%
Command: fa 00 09 01 00 6b 01 05 03 05 00 10 61 8e
Command: fa 00 09 01 00 6b 01 06 03 05 00 0f 65 8e
Command: fa 00 09 01 00 6b 01 06 02 05 00 0f 61 8d
Command: fa 00 09 01 00 6b 01 07 02 05 00 0f 66 8e
Command: fa 00 09 01 00 6b 01 06 03 05 00 0f 65 8e

LDL75%
Command: fa 00 09 01 00 b1 01 06 02 05 00 0f 4d d3
Command: fa 00 09 01 00 b1 01 07 02 05 00 0f 52 d4
Command: fa 00 09 01 00 b1 01 06 02 05 00 0f 4d d3
Command: fa 00 09 01 00 b1 01 07 02 05 00 0f 52 d4
Command: fa 00 09 01 00 b1 01 06 02 05 00 0f 4d d3
Command: fa 00 09 01 00 b1 01 07 02 05 00 0f 52 d4

LDL100% (all right)
Command: fa 00 09 01 00 fc 01 06 02 05 00 0f 5c 1f
Command: fa 00 09 01 00 fc 01 07 02 05 00 0f 61 20
Command: fa 00 09 01 00 fc 01 06 03 05 00 0f 60 20
Command: fa 00 09 01 00 fc 01 05 02 05 00 0f 57 1e
Command: fa 00 09 01 00 fc 01 07 02 05 00 0f 61 20

all left
Command: fa 00 09 01 00 01 02 05 00 03 00 0c 68 1c
Command: fa 00 09 01 00 01 02 05 00 03 00 0d 69 1d
Command: fa 00 09 01 00 01 01 05 00 03 00 0c 62 1b
Command: fa 00 09 01 00 01 01 05 00 03 00 0d 63 1c

NR (25%)
Command: fa 00 09 01 00 01 01 04 00 05 31 0c c5 4d
Command: fa 00 09 01 00 01 01 05 00 06 31 0c cd 4f
Command: fa 00 09 01 00 01 01 05 00 06 31 0c cd 4f
Command: fa 00 09 01 00 01 01 05 00 05 31 0d cb 4f
Command: fa 00 09 01 00 01 01 04 00 06 31 0c c8 4e

NR (50%)
Command: fa 00 09 01 00 01 01 04 00 07 6d 0d 45 8c
Command: fa 00 09 01 00 01 01 05 00 07 6d 0d 4a 8d
Command: fa 00 09 01 00 01 01 04 00 07 6d 0d 45 8c
Command: fa 00 09 01 00 01 01 06 00 08 6d 0c 51 8e
Command: fa 00 09 01 00 01 01 05 00 07 6d 0c 49 8c

NR (75%)
Command: fa 00 09 01 00 00 01 05 00 0a aa 0d c6 cc
Command: fa 00 09 01 00 01 02 05 00 0b aa 0c d5 ce
Command: fa 00 09 01 00 01 01 05 00 0a aa 0c cc cc
Command: fa 00 09 01 00 01 01 05 00 0a aa 0d cd cd
Command: fa 00 09 01 00 01 01 05 00 0a aa 0d cd cd

NR (99%) right
Command: fa 00 09 01 00 01 01 04 00 0d f9 0c 6f 1e
Command: fa 00 09 01 00 01 01 04 00 0d f9 0c 6f 1e
Command: fa 00 09 01 00 01 01 05 00 0d f9 0d 75 20
Command: fa 00 09 01 00 01 01 05 00 0d f9 0c 74 1f
Command: fa 00 09 01 00 01 01 06 00 0d f9 0c 79 20

all left
Command: fa 00 09 01 00 01 01 05 00 03 00 0c 62 1b
Command: fa 00 09 01 00 01 01 05 00 03 00 0c 62 1b
Command: fa 00 09 01 00 01 01 04 00 02 00 0c 5a 19
Command: fa 00 09 01 00 01 02 06 00 03 00 0c 6d 1d
Command: fa 00 09 01 00 01 01 05 00 04 00 0c 65 1c

NT (25%)
Command: fa 00 09 01 00 00 01 04 00 03 00 26 70 33
Command: fa 00 09 01 00 01 01 04 00 03 00 26 77 34
Command: fa 00 09 01 00 01 02 05 00 03 00 26 82 36
Command: fa 00 09 01 00 01 02 05 00 03 00 26 82 36
Command: fa 00 09 01 00 01 01 05 00 03 00 28 7e 37

NT (50%)
Command: fa 00 09 01 00 01 01 05 00 02 00 6c bf 7a
Command: fa 00 09 01 00 01 01 06 00 03 00 6c c7 7c
Command: fa 00 09 01 00 00 02 04 00 02 00 6b b8 78
Command: fa 00 09 01 00 01 02 04 00 03 00 6c c3 7b
Command: fa 00 09 01 00 01 02 05 00 03 00 6b c7 7b

NT (75%)
Command: fa 00 09 01 00 01 02 04 00 02 00 ae 03 bc
Command: fa 00 09 01 00 01 02 05 00 02 00 af 09 be
Command: fa 00 09 01 00 01 02 04 00 02 00 af 04 bd
Command: fa 00 09 01 00 01 02 05 00 02 00 af 09 be
Command: fa 00 09 01 00 00 02 04 00 02 00 af fc bc
Command: fa 00 09 01 00 00 02 04 00 02 00 af fc bc

NT (99%)
Command: fa 00 09 01 00 00 02 04 00 02 00 e8 36 f5
Command: fa 00 09 01 00 01 02 05 00 02 00 e8 42 f7
Command: fa 00 09 01 00 01 02 04 00 03 00 e8 40 f7
Command: fa 00 09 01 00 01 02 05 00 03 00 e7 44 f7
Command: fa 00 09 01 00 00 02 05 00 02 00 e7 3a f5
Command: fa 00 09 01 00 01 02 05 00 02 00 e7 41 f6


All values middle:
Command: fa 00 09 01 00 6f 69 75 6a 3f 6b 72 a7 da
Command: fa 00 09 01 00 6f 69 76 6b 3f 6b 73 b1 dd
Command: fa 00 09 01 00 6f 69 75 6b 3f 6b 72 ab db
Command: fa 00 09 01 00 6f 6a 76 6a 3f 6b 72 b2 dc
Command: fa 00 09 01 00 6f 69 75 6b 3f 6b 73 ac dc

LDL right:
Command: fa 00 09 01 00 fc 6a 76 6a 3e 69 73 8b 68
Command: fa 00 09 01 00 fc 69 75 69 3f 69 73 7f 66
Command: fa 00 09 01 00 fc 6a 75 6b 3e 69 72 89 67
Command: fa 00 09 01 00 fc 69 76 6b 3f 69 72 8b 68

Command: fa 00 09 01 00 fc 6f 74 74 71 6f 66 60 a1
Command: fa 00 09 01 00 fc 6f 73 73 71 6f 66 57 9f
Command: fa 00 09 01 00 fc 6f 74 73 71 6f 66 5c a0
Command: fa 00 09 01 00 fc 6f 75 73 71 6f 67 62 a2

LDL left:
Command: fa 00 09 01 00 01 6f 75 73 71 70 67 80 a7
Command: fa 00 09 01 00 01 6f 75 73 72 70 66 82 a7
Command: fa 00 09 01 00 00 6f 73 73 71 70 66 6e a3
Command: fa 00 09 01 00 01 6f 74 74 71 70 66 7e a6
Command: fa 00 09 01 00 01 6f 73 73 71 70 66 75 a4

LDR right:
Command: fa 00 09 01 00 73 fb 77 6a 3f 6a 73 3c 73
Command: fa 00 09 01 00 73 fb 75 6b 3e 6a 73 33 71
Command: fa 00 09 01 00 73 fb 75 6b 3f 6a 72 35 71
Command: fa 00 09 01 00 73 fb 75 6a 3e 6a 73 2f 70
Command: fa 00 09 01 00 73 fb 75 6b 41 6a 72 3b 73

LDR left:
Command: fa 00 09 01 00 73 02 75 6a 3f 6a 72 55 76
Command: fa 00 09 01 00 73 02 76 6a 3f 6a 72 5a 77
Command: fa 00 09 01 00 73 02 75 6a 3f 6a 72 55 76
Command: fa 00 09 01 00 73 02 75 6a 3f 6a 73 56 77
Command: fa 00 09 01 00 73 02 75 6b 3f 6a 72 59 77

LDR right:
Command: fa 00 09 01 00 73 fc 72 6a 3f 6a 72 28 6e
Command: fa 00 09 01 00 73 fc 70 6a 3f 6a 72 1e 6c
Command: fa 00 09 01 00 73 fb 70 6b 3f 6a 73 1d 6d
Command: fa 00 09 01 00 73 fc 70 6b 3e 6a 72 1f 6c
Command: fa 00 09 01 00 73 fc 6f 6a 3f 6a 72 19 6b

ELR left:
Command: fa 00 09 01 00 73 6b 07 6a 3f 6a 72 a5 71
Command: fa 00 09 01 00 73 6b 07 6a 3f 6a 72 a5 71
Command: fa 00 09 01 00 73 6b 07 6a 3f 6a 72 a5 71
Command: fa 00 09 01 00 73 6b 06 6b 3f 6a 73 a5 72
Command: fa 00 09 01 00 73 6b 07 6b 3f 6a 72 a9 72

ELR right:
Command: fa 00 09 01 00 73 6b f6 6a 3e 6a 73 53 61
Command: fa 00 09 01 00 73 6b f7 6b 3f 6a 73 5f 64
Command: fa 00 09 01 00 73 6b f7 6a 3f 6a 73 5b 63
Command: fa 00 09 01 00 73 6b f7 6b 3f 6a 72 5e 63
Command: fa 00 09 01 00 73 6b f6 69 3f 6a 73 52 61

EUD left:
Command: fa 00 09 01 00 73 6b 5f 00 3f 6a 72 b5 5f
Command: fa 00 09 01 00 73 6b 5f 00 3f 6a 72 b5 5f
Command: fa 00 09 01 00 73 6b 60 00 3f 6a 72 ba 60
Command: fa 00 09 01 00 73 6b 5f 00 3f 6a 72 b5 5f
Command: fa 00 09 01 00 73 6b 61 00 3f 6a 72 bf 61

EUD right:
Command: fa 00 09 01 00 73 6b 62 f7 3f 6a 72 a4 5a
Command: fa 00 09 01 00 73 6b 63 f7 3f 6a 72 a9 5b
Command: fa 00 09 01 00 73 6b 63 f7 3d 6a 72 a3 59
Command: fa 00 09 01 00 73 6b 63 f7 3e 6a 73 a7 5b
Command: fa 00 09 01 00 73 6b 63 f7 3e 6a 73 a7 5b


NE left:
Command: fa 00 09 01 00 73 6b 61 61 04 66 73 8c 84
Command: fa 00 09 01 00 73 6b 61 61 04 66 72 8b 83
Command: fa 00 09 01 00 73 6b 61 61 04 66 72 8b 83
Command: fa 00 09 01 00 73 6b 5f 61 04 66 73 82 82
Command: fa 00 09 01 00 73 6b 61 61 04 66 72 8b 83
Command: fa 00 09 01 00 73 6b 61 61 04 66 72 8b 83

NE right:
Command: fa 00 09 01 00 73 6b 61 61 fa 66 73 71 7b
Command: fa 00 09 01 00 73 6b 60 61 f9 66 73 69 79
Command: fa 00 09 01 00 73 6b 60 61 f9 66 73 69 79
Command: fa 00 09 01 00 73 6b 61 61 f9 66 73 6e 7a
Command: fa 00 09 01 00 73 6b 61 61 f9 66 73 6e 7a

NR left:
Command: fa 00 09 01 00 73 6b 5f 61 60 00 73 ca 78
Command: fa 00 09 01 00 73 6b 61 61 60 00 73 d4 7a
Command: fa 00 09 01 00 73 6b 61 62 60 00 73 d8 7b
Command: fa 00 09 01 00 73 6b 61 61 60 00 73 d4 7a
Command: fa 00 09 01 00 73 6b 60 62 60 00 73 d3 7a

NR right:
Command: fa 00 09 01 00 73 6b 61 62 68 fe 73 ee 82
Command: fa 00 09 01 00 73 6b 60 61 67 fe 73 e2 7f
Command: fa 00 09 01 00 73 6b 5f 61 67 fe 72 dc 7d
Command: fa 00 09 01 00 73 6b 61 61 67 fe 73 e7 80
Command: fa 00 09 01 00 73 6b 61 61 67 fe 73 e7 80

NT left:
Command: fa 00 09 01 00 73 6b 61 61 63 6d 10 55 87
Command: fa 00 09 01 00 73 6b 61 61 63 6d 10 55 87
Command: fa 00 09 01 00 73 6b 61 61 64 6d 10 58 88
Command: fa 00 09 01 00 73 6b 61 61 60 6d 10 4c 84
Command: fa 00 09 01 00 73 6b 61 61 63 6d 10 55 87

NT right:
Command: fa 00 09 01 00 73 6b 60 61 63 6b fd 3a 72
Command: fa 00 09 01 00 73 6b 5f 61 64 6b fd 38 72
Command: fa 00 09 01 00 73 6b 61 62 63 6b fd 43 74
Command: fa 00 09 01 00 73 6b 5f 61 63 6b fc 34 70
Command: fa 00 09 01 00 73 6b 60 61 63 6b fd 3a 72
Command: fa 00 09 01 00 73 6b 60 62 63 6b fd 3e 73

## Command format (based on the output values)

Total bytes per message: 14
Constant value (5 bytes): fa 00 09 01 00
LDL position ( 1 byte)
LDR position (1 byte)
ELR position (1 byte)
EUD position (1 byte)
NE position (1 byte)
NR position (1 byte)
NT position (1 bytes)
crc or similar (2 bytes)

## Read PID Values

fa 00 01 47 35 43

tablet returns pid 
r: fa 00 55 47 3f 4c cc cd 37 51 b7 17 41 00 00 00 3f 4c cc cd 37 51 b7 17 41 00 00 00 40 06 66 66 3b 16 bb 99 41 80 00 00 40 06 66 66 3b 16 bb 99 41 80 00 00 3f 80 00 00 3a a3 d7 0a 3c 03 12 6f 3e 99 99 9a 3a 83 12 6f 3d a3 d7 0a 3f 00 00 00 3a 83 12 6f 3d a3 d7 0a ce 9b

## Reset PID values

#todo

## Slow blink

fa 00 0f 01 60 84 16 16 14 fc fc 3c 0b 0b 3c 16 16 0a bf ee

return same as when doing movements or as when reading VR
Command: fa 00 09 01 00 14 14 60 62 64 6b 66 02 26
Command: fa 00 09 01 00 14 14 61 61 64 6b 66 03 26
Command: fa 00 09 01 00 14 14 60 61 64 6b 66 fd 25
Command: fa 00 09 01 00 14 14 60 62 64 6b 65 01 25
Command: fa 00 09 01 00 14 14 60 62 64 6b 66 02 26
Command: fa 00 09 01 00 14 14 60 61 64 6b 66 fd 25
Command: fa 00 09 01 00 14 14 60 61 64 6b 65 fc 24
Command: fa 00 09 01 00 14 14 60 61 63 6b 66 fa 24


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

 r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

 ## CAL LDR
 Calibration of right eyelid

 fa 00 02 43 20 93 60

 r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

 ## CAL ELR:
 Calibration of horizontal eye movements

 fa 00 02 43 10 83 50

 r: fa 00 02 43 00 73 40 (all calibrations have the same answer)


 ## CAL EUD
 Calibration of vertical eye movement

fa 00 02 43 08 7b 48

r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

## CAL NE
Calibration of vertical head movement

fa 00 02 43 04 77 44

r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

## CAL NR
Calibration of horizontal head movement

fa 00 02 43 02 75 42

r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

## CAL NT
Calibration of head tilt

fa 00 02 43 01 74 41

r: fa 00 02 43 00 73 40 (all calibrations have the same answer)

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

## Response for movement

All the movements generate several chunks of data as responses, (similar to read VR)

example:

Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 09 01 00 6e 78 7c 77 68 64 76 c3 23
Command: fa 00 09 01 00 6e 78 7a 77 68 64 76 b9 21
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 09 01 00 6e 77 7a 77 68 64 77 b4 21
Command: fa 00 09 01 00 6e 78 7a 77 69 64 76 bc 22
Command: fa 00 09 01 00 6e 77 79 77 68 64 76 ae 1f
Command: fa 00 09 01 00 6e 78 7a 77 68 64 75 b8 20
Command: fa 00 09 01 00 6e 78 7b 77 68 64 75 bd 21
Command: fa 00 09 01 00 6e 78 7c 77 68 64 76 c3 23
Command: fa 00 09 01 00 6e 78 7a 77 68 64 75 b8 20
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 09 01 00 6e 78 7b 77 68 64 75 bd 21
Command: fa 00 09 01 00 6e 78 7a 77 68 64 75 b8 20
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 09 01 00 6e 78 7b 77 69 64 76 c1 23
Command: fa 00 09 01 00 6e 77 7a 77 68 64 76 b3 20
Command: fa 00 09 01 00 6e 78 7b 77 65 64 76 b5 1f

Sometimes it outputs this in between commands:
Command: fa 00 09 01 00 6e 77 7b 77 69 64 76 bb 22
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22
Command: fa 00 03 02 6e 08 d8 76
Command: fa 00 09 01 00 6e 78 7a
Command: fa 00 09 01 00 6e 77 7a 77 68 64 76 b3 20
Command: fa 00 09 01 00 6e 78 7a 77 68 64 76 b9 21
Command: fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22

Command: fa 00 03 02 6e 40 11 ae
Command: fa 00 09 01 00 fc 01 07
The talet says that this is an error when the motor did not achieve the desired position.

## CRC hunt

last 2 bytes might be a crc or something similar. The objective is to analyze

interesting things:

1. For sending commands, the last byte is equal to the 5th plus one
2. also in this case, last 2 bytes are the same either if the previous are 00 or ff

(40 - 41)
fa 00 04 01 40 01 ff b7 41
fa 00 04 01 40 01 00 b7 41

(20 - 21)
fa 00 04 01 20 01 ff 57 21
fa 00 04 01 20 01 00 57 21

(10 - 11)
fa 00 04 01 10 01 ff 27 11
fa 00 04 01 10 01 00 27 11

(08 - 09)
fa 00 04 01 08 01 ff 0f 09
fa 00 04 01 08 01 00 0f 09

(04 - 05)
fa 00 04 01 04 01 ff 03 05
fa 00 04 01 04 01 00 03 05

Here are the codes for sending commands 
Command: fa 00 04 01 01 01 00 f9 02
Command: fa 00 04 01 02 01 00 fc 03
Command: fa 00 04 01 04 01 00 03 05
Command: fa 00 04 01 08 01 00 0f 09
Command: fa 00 04 01 10 01 00 27 11
Command: fa 00 04 01 20 01 00 57 21
Command: fa 00 04 01 40 01 00 b7 41
byte 0 - 1 - 2 - 3 - 4- 5 - 6 - 7 - 8
b8 = x + b4
b7 = f(b4)

b4 vs b7
01 - f9
02 - fc
04 - 03
08 - 0f
10 - 27
20 - 57
40 - b7

Calibration commands

fa 00 02 43 40 b3 80
fa 00 02 43 20 93 60
fa 00 02 43 10 83 50
fa 00 02 43 08 7b 48
fa 00 02 43 04 77 44
fa 00 02 43 02 75 42
fa 00 02 43 01 74 41
byte 0 - 1 - 2 - 3 - 4 - 5 - 6

In calibration commands, the last 2 byte depend to byte 4. 
byte 6(b6) = x + b4
b5 = y + b4


### Data dump for analysis

Command: fa 00 09 01 00 00 02 05 00 02 00 e8 3b f6
Command: fa 00 09 01 00 01 02 04 00 02 00 e7 3c f5
Command: fa 00 09 01 00 01 02 05 00 03 00 e7 44 f7
Command: fa 00 09 01 00 01 02 04 00 02 00 e7 3c f5
Command: fa 00 09 01 00 00 02 05 00 02 00 e7 3a f5
Command: fa 00 09 01 00 00 02 05 00 02 00 e8 3b f6
Command: fa 00 09 01 00 01 02 06 00 02 00 e7 46 f7
Command: fa 00 09 01 00 01 02 07 00 02 00 e8 4c f9
Command: fa 00 09 01 00 00 02 03 00 02 00 e7 30 f3
Command: fa 00 09 01 00 01 02 05 00 03 00 e8 45 f8
Command: fa 00 09 01 00 01 02 05 00 03 00 e7 44 f7
Command: fa 00 09 01 00 01 02 04 00 02 00 e7 3c f5
Command: fa 00 09 01 00 01 02 05 00 02 00 e8 42 f7
Command: fa 00 09 01 00 00 02 04 00 02 00 e7 35 f4
Command: fa 00 09 01 00 00 02 04 00 03 00 e7 38 f5
Command: fa 00 09 01 00 01 02 04 00 03 00 e8 40 f7
Command: fa 00 09 01 00 00 02 06 00 02 00 e8 40 f7
Command: fa 00 09 01 00 00 02 04 00 02 00 e8 36 f5
Command: fa 00 09 01 00 01 02 05 00 02 00 e8 42 f7
Command: fa 00 09 01 00 01 02 04 00 03 00 e8 40 f7
Command: fa 00 09 01 00 01 02 05 00 03 00 e7 44 f7
Command: fa 00 09 01 00 00 02 05 00 02 00 e7 3a f5
Command: fa 00 09 01 00 01 02 05 00 02 00 e7 41 f6

Command: fa 00 09 01 00 7e 52 46 7f b4 7e 6b 6e 3a
Command: fa 00 09 01 00 7e 52 46 7f b4 7f 6b 70 3b
Command: fa 00 09 01 00 7e 52 46 7f b4 80 6b 72 3c
Command: fa 00 09 01 00 7e 52 45 7f b5 80 6a 6f 3b
Command: fa 00 09 01 00 7e 53 46 7f b4 81 6b 7a 3e
Command: fa 00 09 01 00 7e 53 46 7f b4 81 6b 7a 3e
Command: fa 00 09 01 00 7e 52 45 7f b4 81 6b 6f 3c
Command: fa 00 09 01 00 7e 53 47 7f b5 82 6b 84 41
Command: fa 00 09 01 00 7e 53 46 7f b4 82 6a 7b 3e
Command: fa 00 09 01 00 7e 52 45 7f b4 82 6b 71 3d
Command: fa 00 09 01 00 7e 53 45 7f b4 82 6b 77 3e
Command: fa 00 09 01 00 7e 52 46 7f b4 82 6b 76 3e
Command: fa 00 09 01 00 7e 53 45 7f b5 82 6b 7a 3f
Command: fa 00 09 01 00 7e 53 46 7f b4 82 6b 7c 3f
Command: fa 00 09 01 00 7e 53 45 7f b4 82 6b 77 3e
Command: fa 00 09 01 00 7e 53 45 7f b5 82 6b 7a 3f
Command: fa 00 09 01 00 7e 53 46 7f b4 82 6a 7b 3e
Command: fa 00 09 01 00 7e 52 45 7f b4 82 6b 71 3d
Command: fa 00 09 01 00 7e 52 46 7f b4 82 6b 76 3e
Command: fa 00 09 01 00 7e 52 45 7f b5 82 6b 74 3e
Command: fa 00 09 01 00 7e 52 46 7f b4 82 6b 76 3e
Command: fa 00 09 01 00 7e 53 45 7f b4 82 6b 77 3e
Command: fa 00 09 01 00 7e 52 46 7f b4 82 6a 75 3d
Command: fa 00 09 01 00 7e 53 45 7f b4 82 6b 77 3e
Command: fa 00 09 01 00 7e 52 45 7f b4 80 6b 6d 3b
Command: fa 00 09 01 00 7e 53 45 7f b4 7e 6b 6f 3a
Command: fa 00 09 01 00 7e 52 46 7f b5 7c 6b 6d 39
Command: fa 00 09 01 00 7e 52 46 7f b4 7b 6b 68 37
Command: fa 00 09 01 00 7e 52 46 7f b4 79 6b 64 35
Command: fa 00 09 01 00 7e 53 46 7f b4 77 6b 66 34
Command: fa 00 09 01 00 7e 52 45 7f b4 76 6b 59 31
Command: fa 00 09 01 00 7e 53 45 7f b4 74 6b 5b 30
Command: fa 00 09 01 00 7e 52 45 7f b4 72 6b 51 2d
Command: fa 00 09 01 00 7e 53 45 7f b4 71 6b 55 2d
Command: fa 00 09 01 00 7e 53 46 7e b4 6f 6a 51 2a
Command: fa 00 09 01 00 7e 53 45 7f b4 6e 6b 4f 2a
Command: fa 00 09 01 00 7e 53 45 7f b4 6c 6b 4b 28
Command: fa 00 09 01 00 7e 53 45 7f b4 6a 6b 47 26
Command: fa 00 09 01 00 7e 53 46 7f b4 69 6a 49 25
Command: fa 00 09 01 00 7e 53 46 7f b4 67 6a 45 23
Command: fa 00 09 01 00 7e 53 45 7f b4 66 6a 3e 21
Command: fa 00 09 01 00 7e 52 46 7f b4 64 6b 3a 20
Command: fa 00 09 01 00 7e 53 46 7f b4 62 6a 3b 1e
Command: fa 00 09 01 00 7e 52 46 7f b4 61 6b 34 1d
Command: fa 00 09 01 00 7e 52 46 7f b4 60 6a 31 1b
Command: fa 00 09 01 00 7e 52 46 7f b4 5e 6b 2e 1a
Command: fa 00 09 01 00 7e 53 46 7f b4 5d 6b 32 1a
Command: fa 00 09 01 00 7e 53 46 7f b4 5c 6a 2f 18
Command: fa 00 09 01 00 7e 52 44 7f b4 5b 6b 1e 15
Command: fa 00 09 01 00 7e 53 45 7f b4 5a 6b 27 16
Command: fa 00 09 01 00 7e 53 46 7f b4 5a 6a 2b 16
Command: fa 00 09 01 00 7e 53 46 7f b3 59 6b 27 15
Command: fa 00 09 01 00 7e 53 45 7f b3 58 6b 20 13
Command: fa 00 09 01 00 7e 53 45 7f b4 58 6b 23 14
Command: fa 00 09 01 00 7e 52 46 7f b4 57 6b 20 13
Command: fa 00 09 01 00 7e 53 46 7f b3 57 6b 23 13
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6b 16 10
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6a 1e 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6b 16 10
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6a 1e 11
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6a 1b 10
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6b 16 10
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6b 1c 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6a 20 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6b 1c 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 46 7f b3 56 6b 1b 11
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6a 1b 10
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6a 1e 11
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6b 16 10
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6a 1d 11
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6a 1d 11
Command: fa 00 09 01 00 7e 53 46 7f b4 56 6b 24 13
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 46 7e b3 56 6b 17 10
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6a 18 10
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 44 7f b3 56 6b 11 0f
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6b 1c 11
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 52 46 7f b4 57 6b 20 13
Command: fa 00 09 01 00 7e 52 46 7e b3 56 6b 17 10
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 52 46 7f b3 56 6b 1b 11
Command: fa 00 09 01 00 7e 52 46 7f b3 56 6b 1b 11
Command: fa 00 09 01 00 7e 53 45 7f b3 56 6b 1c 11
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6b 16 10
Command: fa 00 09 01 00 7e 53 46 7f b4 56 6b 24 13
Command: fa 00 09 01 00 7e 53 46 7f b4 56 6b 24 13
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 46 7f b4 56 6a 23 12
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6b 1f 12
Command: fa 00 09 01 00 7e 53 45 7f b4 56 6a 1e 11
Command: fa 00 09 01 00 7e 53 46 7f b3 56 6b 21 12
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 45 7f b4 56 6b 19 11
Command: fa 00 09 01 00 7e 52 46 7f b4 56 6b 1e 12
Command: fa 00 09 01 00 7e 52 45 7f b3 56 6a 15 0f
Command: fa 00 09 01 00 7e 52 43 7f b4 56 6b 0f 0f

Command: fa 00 04 01 40 01 6d 25 ae
Command: fa 00 04 01 40 01 64 1c a5
Command: fa 00 04 01 40 01 5d 15 9e
Command: fa 00 04 01 40 01 55 0d 96
Command: fa 00 04 01 40 01 4e 06 8f
Command: fa 00 04 01 40 01 4c 04 8d
Command: fa 00 04 01 40 01 48 00 89
Command: fa 00 04 01 40 01 44 fb 85
Command: fa 00 04 01 40 01 43 fa 84
Command: fa 00 04 01 40 01 40 f7 81
Command: fa 00 04 01 40 01 40 f7 81
Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 03 ba 44
Command: fa 00 04 01 40 01 05 bc 46
Command: fa 00 04 01 40 01 08 bf 49
Command: fa 00 04 01 40 01 0a c1 4b
Command: fa 00 04 01 40 01 0d c4 4e
Command: fa 00 04 01 40 01 10 c7 51
Command: fa 00 04 01 40 01 12 c9 53
Command: fa 00 04 01 40 01 15 cc 56
Command: fa 00 04 01 40 01 17 ce 58
Command: fa 00 04 01 40 01 19 d0 5a
Command: fa 00 04 01 40 01 1c d3 5d
Command: fa 00 04 01 40 01 1f d6 60
Command: fa 00 04 01 40 01 21 d8 62
Command: fa 00 04 01 40 01 24 db 65
Command: fa 00 04 01 40 01 26 dd 67
Command: fa 00 04 01 40 01 29 e0 6a
Command: fa 00 04 01 40 01 2c e3 6d
Command: fa 00 04 01 40 01 2e e5 6f
Command: fa 00 04 01 40 01 31 e8 72
Command: fa 00 04 01 40 01 34 eb 75
Command: fa 00 04 01 40 01 36 ed 77
Command: fa 00 04 01 40 01 39 f0 7a
Command: fa 00 04 01 40 01 3b f2 7c
Command: fa 00 04 01 40 01 3e f5 7f
Command: fa 00 04 01 40 01 41 f8 82
Command: fa 00 04 01 40 01 43 fa 84
Command: fa 00 04 01 40 01 46 fd 87
Command: fa 00 04 01 40 01 48 00 89
Command: fa 00 04 01 40 01 4b 03 8c
Command: fa 00 04 01 40 01 4e 06 8f
Command: fa 00 04 01 40 01 50 08 91
Command: fa 00 04 01 40 01 53 0b 94
Command: fa 00 04 01 40 01 55 0d 96
Command: fa 00 04 01 40 01 58 10 99
Command: fa 00 04 01 40 01 5b 13 9c
Command: fa 00 04 01 40 01 5d 15 9e
Command: fa 00 04 01 40 01 60 18 a1
Command: fa 00 04 01 40 01 62 1a a3
Command: fa 00 04 01 40 01 65 1d a6
Command: fa 00 04 01 40 01 68 20 a9
Command: fa 00 04 01 40 01 6a 22 ab
Command: fa 00 04 01 40 01 6d 25 ae
Command: fa 00 04 01 40 01 70 28 b1
Command: fa 00 04 01 40 01 72 2a b3
Command: fa 00 04 01 40 01 75 2d b6
Command: fa 00 04 01 40 01 77 2f b8
Command: fa 00 04 01 40 01 7a 32 bb
Command: fa 00 04 01 40 01 7d 35 be
Command: fa 00 04 01 40 01 7f 37 c0
Command: fa 00 04 01 40 01 82 3a c3
Command: fa 00 04 01 40 01 84 3c c5
Command: fa 00 04 01 40 01 87 3f c8
Command: fa 00 04 01 40 01 8a 42 cb
Command: fa 00 04 01 40 01 8c 44 cd
Command: fa 00 04 01 40 01 8f 47 d0
Command: fa 00 04 01 40 01 91 49 d2
Command: fa 00 04 01 40 01 94 4c d5
Command: fa 00 04 01 40 01 97 4f d8
Command: fa 00 04 01 40 01 99 51 da
Command: fa 00 04 01 40 01 9c 54 dd
Command: fa 00 04 01 40 01 9e 56 df
Command: fa 00 04 01 40 01 a1 59 e2
Command: fa 00 04 01 40 01 a4 5c e5
Command: fa 00 04 01 40 01 a6 5e e7
Command: fa 00 04 01 40 01 a9 61 ea
Command: fa 00 04 01 40 01 ac 64 ed
Command: fa 00 04 01 40 01 ae 66 ef
Command: fa 00 04 01 40 01 b1 69 f2
Command: fa 00 04 01 40 01 b3 6b f4
Command: fa 00 04 01 40 01 b6 6e f7
Command: fa 00 04 01 40 01 b9 71 fa
Command: fa 00 04 01 40 01 bb 73 fc
Command: fa 00 04 01 40 01 be 76 00
Command: fa 00 04 01 40 01 c0 78 02
Command: fa 00 04 01 40 01 c3 7b 05
Command: fa 00 04 01 40 01 c6 7e 08
Command: fa 00 04 01 40 01 c8 80 0a
Command: fa 00 04 01 40 01 cb 83 0d
Command: fa 00 04 01 40 01 cd 85 0f
Command: fa 00 04 01 40 01 d0 88 12
Command: fa 00 04 01 40 01 d3 8b 15
Command: fa 00 04 01 40 01 d5 8d 17
Command: fa 00 04 01 40 01 d8 90 1a
Command: fa 00 04 01 40 01 da 92 1c
Command: fa 00 04 01 40 01 e0 98 22
Command: fa 00 04 01 40 01 e8 a0 2a
Command: fa 00 04 01 40 01 ea a2 2c
Command: fa 00 04 01 40 01 ef a7 31
Command: fa 00 04 01 40 01 f5 ad 37
Command: fa 00 04 01 40 01 f7 af 39
Command: fa 00 04 01 40 01 fa b2 3c
Command: fa 00 04 01 40 01 fc b4 3e
Command: fa 00 04 01 40 01 ff b7 41

Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 01 b8 42
Command: fa 00 04 01 40 01 04 bb 45
Command: fa 00 04 01 40 01 07 be 48
Command: fa 00 04 01 40 01 09 c0 4a
Command: fa 00 04 01 40 01 07 be 48
Command: fa 00 04 01 40 01 04 bb 45
Command: fa 00 04 01 40 01 01 b8 42
Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 00 b7 41
Command: fa 00 04 01 40 01 01 b8 42
Command: fa 00 04 01 40 01 04 bb 45
Command: fa 00 04 01 40 01 07 be 48
Command: fa 00 04 01 40 01 09 c0 4a
Command: fa 00 04 01 40 01 0c c3 4d
Command: fa 00 04 01 40 01 0e c5 4f
Command: fa 00 04 01 40 01 11 c8 52
Command: fa 00 04 01 40 01 14 cb 55
Command: fa 00 04 01 40 01 16 cd 57
Command: fa 00 04 01 40 01 19 d0 5a
Command: fa 00 04 01 40 01 1b d2 5c
Command: fa 00 04 01 40 01 1e d5 5f
Command: fa 00 04 01 40 01 21 d8 62
Command: fa 00 04 01 40 01 23 da 64
Command: fa 00 04 01 40 01 26 dd 67
Command: fa 00 04 01 40 01 28 df 69
Command: fa 00 04 01 40 01 2b e2 6c
Command: fa 00 04 01 40 01 2e e5 6f
Command: fa 00 04 01 40 01 30 e7 71
Command: fa 00 04 01 40 01 33 ea 74
Command: fa 00 04 01 40 01 35 ec 76
Command: fa 00 04 01 40 01 38 ef 79
Command: fa 00 04 01 40 01 3b f2 7c
Command: fa 00 04 01 40 01 3d f4 7e
Command: fa 00 04 01 40 01 40 f7 81
Command: fa 00 04 01 40 01 43 fa 84
Command: fa 00 04 01 40 01 45 fc 86
Command: fa 00 04 01 40 01 48 00 89
Command: fa 00 04 01 40 01 4a 02 8b
Command: fa 00 04 01 40 01 4d 05 8e
Command: fa 00 04 01 40 01 50 08 91
Command: fa 00 04 01 40 01 52 0a 93
Command: fa 00 04 01 40 01 55 0d 96
Command: fa 00 04 01 40 01 57 0f 98
Command: fa 00 04 01 40 01 5a 12 9b
Command: fa 00 04 01 40 01 5d 15 9e
Command: fa 00 04 01 40 01 5f 17 a0
Command: fa 00 04 01 40 01 62 1a a3
Command: fa 00 04 01 40 01 64 1c a5
Command: fa 00 04 01 40 01 67 1f a8
Command: fa 00 04 01 40 01 6a 22 ab
Command: fa 00 04 01 40 01 6c 24 ad
Command: fa 00 04 01 40 01 6f 27 b0
Command: fa 00 04 01 40 01 71 29 b2
Command: fa 00 04 01 40 01 74 2c b5
Command: fa 00 04 01 40 01 77 2f b8
Command: fa 00 04 01 40 01 79 31 ba
Command: fa 00 04 01 40 01 7c 34 bd
Command: fa 00 04 01 40 01 7f 37 c0
Command: fa 00 04 01 40 01 81 39 c2
Command: fa 00 04 01 40 01 84 3c c5
Command: fa 00 04 01 40 01 86 3e c7
Command: fa 00 04 01 40 01 89 41 ca
Command: fa 00 04 01 40 01 8c 44 cd
Command: fa 00 04 01 40 01 8e 46 cf
Command: fa 00 04 01 40 01 91 49 d2
Command: fa 00 04 01 40 01 93 4b d4
Command: fa 00 04 01 40 01 96 4e d7
Command: fa 00 04 01 40 01 99 51 da
Command: fa 00 04 01 40 01 9b 53 dc
Command: fa 00 04 01 40 01 9e 56 df
Command: fa 00 04 01 40 01 a0 58 e1
Command: fa 00 04 01 40 01 a3 5b e4
Command: fa 00 04 01 40 01 a6 5e e7
Command: fa 00 04 01 40 01 a8 60 e9
Command: fa 00 04 01 40 01 ab 63 ec
Command: fa 00 04 01 40 01 ad 65 ee
Command: fa 00 04 01 40 01 b0 68 f1
Command: fa 00 04 01 40 01 b3 6b f4
Command: fa 00 04 01 40 01 b5 6d f6
Command: fa 00 04 01 40 01 b8 70 f9
Command: fa 00 04 01 40 01 bb 73 fc
Command: fa 00 04 01 40 01 bd 75 fe
Command: fa 00 04 01 40 01 c0 78 02
Command: fa 00 04 01 40 01 c2 7a 04
Command: fa 00 04 01 40 01 c5 7d 07
Command: fa 00 04 01 40 01 c8 80 0a
Command: fa 00 04 01 40 01 ca 82 0c
Command: fa 00 04 01 40 01 cd 85 0f
Command: fa 00 04 01 40 01 cf 87 11
Command: fa 00 04 01 40 01 d2 8a 14
Command: fa 00 04 01 40 01 d5 8d 17
Command: fa 00 04 01 40 01 d7 8f 19
Command: fa 00 04 01 40 01 da 92 1c
Command: fa 00 04 01 40 01 dc 94 1e
Command: fa 00 04 01 40 01 df 97 21
Command: fa 00 04 01 40 01 e2 9a 24
Command: fa 00 04 01 40 01 e4 9c 26
Command: fa 00 04 01 40 01 e7 9f 29
Command: fa 00 04 01 40 01 e9 a1 2b
Command: fa 00 04 01 40 01 ec a4 2e
Command: fa 00 04 01 40 01 ef a7 31
Command: fa 00 04 01 40 01 f1 a9 33
Command: fa 00 04 01 40 01 f4 ac 36
Command: fa 00 04 01 40 01 f7 af 39
Command: fa 00 04 01 40 01 f9 b1 3b
Command: fa 00 04 01 40 01 fc b4 3e
Command: fa 00 04 01 40 01 fe b6 40
Command: fa 00 04 01 40 01 ff b7 41

Command: fa 00 04 01 20 01 00 57 21
Command: fa 00 04 01 20 01 08 5f 29
Command: fa 00 04 01 20 01 13 6a 34
Command: fa 00 04 01 20 01 16 6d 37
Command: fa 00 04 01 20 01 10 67 31
Command: fa 00 04 01 20 01 0e 65 2f
Command: fa 00 04 01 20 01 01 58 22
Command: fa 00 04 01 20 01 00 57 21
Command: fa 00 04 01 20 01 08 5f 29
Command: fa 00 04 01 20 01 0b 62 2c
Command: fa 00 04 01 20 01 0e 65 2f
Command: fa 00 04 01 20 01 10 67 31
Command: fa 00 04 01 20 01 13 6a 34
Command: fa 00 04 01 20 01 18 6f 39
Command: fa 00 04 01 20 01 1d 74 3e
Command: fa 00 04 01 20 01 25 7c 46
Command: fa 00 04 01 20 01 28 7f 49
Command: fa 00 04 01 20 01 2d 84 4e
Command: fa 00 04 01 20 01 30 87 51
Command: fa 00 04 01 20 01 35 8c 56
Command: fa 00 04 01 20 01 37 8e 58
Command: fa 00 04 01 20 01 39 90 5a
Command: fa 00 04 01 20 01 3c 93 5d
Command: fa 00 04 01 20 01 3f 96 60
Command: fa 00 04 01 20 01 41 98 62
Command: fa 00 04 01 20 01 49 a0 6a
Command: fa 00 04 01 20 01 4c a3 6d
Command: fa 00 04 01 20 01 4e a5 6f
Command: fa 00 04 01 20 01 51 a8 72
Command: fa 00 04 01 20 01 53 aa 74
Command: fa 00 04 01 20 01 56 ad 77
Command: fa 00 04 01 20 01 59 b0 7a
Command: fa 00 04 01 20 01 5b b2 7c
Command: fa 00 04 01 20 01 5d b4 7e
Command: fa 00 04 01 20 01 62 b9 83
Command: fa 00 04 01 20 01 65 bc 86
Command: fa 00 04 01 20 01 68 bf 89
Command: fa 00 04 01 20 01 6a c1 8b
Command: fa 00 04 01 20 01 6d c4 8e
Command: fa 00 04 01 20 01 72 c9 93
Command: fa 00 04 01 20 01 77 ce 98
Command: fa 00 04 01 20 01 82 d9 a3
Command: fa 00 04 01 20 01 84 db a5
Command: fa 00 04 01 20 01 87 de a8
Command: fa 00 04 01 20 01 8f e6 b0
Command: fa 00 04 01 20 01 94 eb b5
Command: fa 00 04 01 20 01 9c f3 bd
Command: fa 00 04 01 20 01 9e f5 bf
Command: fa 00 04 01 20 01 a9 01 ca
Command: fa 00 04 01 20 01 b3 0b d4
Command: fa 00 04 01 20 01 b9 11 da
Command: fa 00 04 01 20 01 bb 13 dc
Command: fa 00 04 01 20 01 c0 18 e1
Command: fa 00 04 01 20 01 c3 1b e4
Command: fa 00 04 01 20 01 c8 20 e9
Command: fa 00 04 01 20 01 cb 23 ec
Command: fa 00 04 01 20 01 d0 28 f1
Command: fa 00 04 01 20 01 d5 2d f6
Command: fa 00 04 01 20 01 e2 3a 04
Command: fa 00 04 01 20 01 f2 4a 14
Command: fa 00 04 01 20 01 f7 4f 19
Command: fa 00 04 01 20 01 fa 52 1c
Command: fa 00 04 01 20 01 f2 4a 14
Command: fa 00 04 01 20 01 ff 57 21

Command: fa 00 04 01 10 01 02 29 13
Command: fa 00 04 01 10 01 02 29 13
Command: fa 00 04 01 10 01 00 27 11
Command: fa 00 04 01 10 01 02 29 13
Command: fa 00 04 01 10 01 05 2c 16
Command: fa 00 04 01 10 01 07 2e 18
Command: fa 00 04 01 10 01 0a 31 1b
Command: fa 00 04 01 10 01 0c 33 1d
Command: fa 00 04 01 10 01 0f 36 20
Command: fa 00 04 01 10 01 12 39 23
Command: fa 00 04 01 10 01 14 3b 25
Command: fa 00 04 01 10 01 17 3e 28
Command: fa 00 04 01 10 01 19 40 2a
Command: fa 00 04 01 10 01 1c 43 2d
Command: fa 00 04 01 10 01 1f 46 30
Command: fa 00 04 01 10 01 21 48 32
Command: fa 00 04 01 10 01 24 4b 35
Command: fa 00 04 01 10 01 26 4d 37
Command: fa 00 04 01 10 01 29 50 3a
Command: fa 00 04 01 10 01 2c 53 3d
Command: fa 00 04 01 10 01 2e 55 3f
Command: fa 00 04 01 10 01 31 58 42
Command: fa 00 04 01 10 01 34 5b 45
Command: fa 00 04 01 10 01 36 5d 47
Command: fa 00 04 01 10 01 39 60 4a
Command: fa 00 04 01 10 01 3b 62 4c
Command: fa 00 04 01 10 01 3e 65 4f
Command: fa 00 04 01 10 01 41 68 52
Command: fa 00 04 01 10 01 43 6a 54
Command: fa 00 04 01 10 01 46 6d 57
Command: fa 00 04 01 10 01 48 6f 59
Command: fa 00 04 01 10 01 4b 72 5c
Command: fa 00 04 01 10 01 4e 75 5f
Command: fa 00 04 01 10 01 50 77 61
Command: fa 00 04 01 10 01 53 7a 64
Command: fa 00 04 01 10 01 55 7c 66
Command: fa 00 04 01 10 01 58 7f 69
Command: fa 00 04 01 10 01 5b 82 6c
Command: fa 00 04 01 10 01 5d 84 6e
Command: fa 00 04 01 10 01 60 87 71
Command: fa 00 04 01 10 01 62 89 73
Command: fa 00 04 01 10 01 65 8c 76
Command: fa 00 04 01 10 01 68 8f 79
Command: fa 00 04 01 10 01 6a 91 7b
Command: fa 00 04 01 10 01 6d 94 7e
Command: fa 00 04 01 10 01 70 97 81
Command: fa 00 04 01 10 01 72 99 83
Command: fa 00 04 01 10 01 75 9c 86
Command: fa 00 04 01 10 01 77 9e 88
Command: fa 00 04 01 10 01 7a a1 8b
Command: fa 00 04 01 10 01 7d a4 8e
Command: fa 00 04 01 10 01 7f a6 90
Command: fa 00 04 01 10 01 82 a9 93
Command: fa 00 04 01 10 01 84 ab 95
Command: fa 00 04 01 10 01 87 ae 98
Command: fa 00 04 01 10 01 8a b1 9b
Command: fa 00 04 01 10 01 8c b3 9d
Command: fa 00 04 01 10 01 8f b6 a0
Command: fa 00 04 01 10 01 91 b8 a2
Command: fa 00 04 01 10 01 94 bb a5
Command: fa 00 04 01 10 01 97 be a8
Command: fa 00 04 01 10 01 99 c0 aa
Command: fa 00 04 01 10 01 9c c3 ad
Command: fa 00 04 01 10 01 9e c5 af
Command: fa 00 04 01 10 01 a1 c8 b2
Command: fa 00 04 01 10 01 a4 cb b5
Command: fa 00 04 01 10 01 a6 cd b7
Command: fa 00 04 01 10 01 a9 d0 ba
Command: fa 00 04 01 10 01 ac d3 bd
Command: fa 00 04 01 10 01 ae d5 bf
Command: fa 00 04 01 10 01 b1 d8 c2
Command: fa 00 04 01 10 01 b3 da c4
Command: fa 00 04 01 10 01 b6 dd c7
Command: fa 00 04 01 10 01 b9 e0 ca
Command: fa 00 04 01 10 01 bb e2 cc
Command: fa 00 04 01 10 01 be e5 cf
Command: fa 00 04 01 10 01 c0 e7 d1
Command: fa 00 04 01 10 01 c3 ea d4
Command: fa 00 04 01 10 01 c6 ed d7
Command: fa 00 04 01 10 01 c8 ef d9
Command: fa 00 04 01 10 01 cb f2 dc
Command: fa 00 04 01 10 01 cd f4 de
Command: fa 00 04 01 10 01 d0 f7 e1
Command: fa 00 04 01 10 01 d3 fa e4
Command: fa 00 04 01 10 01 d5 fc e6
Command: fa 00 04 01 10 01 d8 00 e9
Command: fa 00 04 01 10 01 da 02 eb
Command: fa 00 04 01 10 01 dd 05 ee
Command: fa 00 04 01 10 01 e0 08 f1
Command: fa 00 04 01 10 01 e2 0a f3
Command: fa 00 04 01 10 01 e5 0d f6
Command: fa 00 04 01 10 01 e8 10 f9
Command: fa 00 04 01 10 01 ea 12 fb
Command: fa 00 04 01 10 01 ed 15 fe
Command: fa 00 04 01 10 01 ef 17 01
Command: fa 00 04 01 10 01 f2 1a 04
Command: fa 00 04 01 10 01 f5 1d 07
Command: fa 00 04 01 10 01 f7 1f 09
Command: fa 00 04 01 10 01 fa 22 0c
Command: fa 00 04 01 10 01 fc 24 0e
Command: fa 00 04 01 10 01 ff 27 11
Command: fa 00 04 01 10 01 fb 23 0d
Command: fa 00 04 01 10 01 f5 1d 07
Command: fa 00 04 01 10 01 ef 17 01
Command: fa 00 04 01 10 01 e9 11 fa
Command: fa 00 04 01 10 01 e4 0c f5
Command: fa 00 04 01 10 01 e0 08 f1
Command: fa 00 04 01 10 01 dc 04 ed
Command: fa 00 04 01 10 01 d9 01 ea
Command: fa 00 04 01 10 01 d5 fc e6
Command: fa 00 04 01 10 01 d2 f9 e3
Command: fa 00 04 01 10 01 cb f2 dc
Command: fa 00 04 01 10 01 c7 ee d8
Command: fa 00 04 01 10 01 c2 e9 d3
Command: fa 00 04 01 10 01 be e5 cf
Command: fa 00 04 01 10 01 bb e2 cc
Command: fa 00 04 01 10 01 b7 de c8
Command: fa 00 04 01 10 01 b3 da c4
Command: fa 00 04 01 10 01 af d6 c0
Command: fa 00 04 01 10 01 ab d2 bc
Command: fa 00 04 01 10 01 a7 ce b8
Command: fa 00 04 01 10 01 a2 c9 b3
Command: fa 00 04 01 10 01 9e c5 af
Command: fa 00 04 01 10 01 9a c1 ab
Command: fa 00 04 01 10 01 95 bc a6
Command: fa 00 04 01 10 01 90 b7 a1
Command: fa 00 04 01 10 01 88 af 99
Command: fa 00 04 01 10 01 83 aa 94
Command: fa 00 04 01 10 01 7f a6 90
Command: fa 00 04 01 10 01 79 a0 8a
Command: fa 00 04 01 10 01 75 9c 86
Command: fa 00 04 01 10 01 70 97 81
Command: fa 00 04 01 10 01 6a 91 7b
Command: fa 00 04 01 10 01 66 8d 77
Command: fa 00 04 01 10 01 61 88 72
Command: fa 00 04 01 10 01 58 7f 69
Command: fa 00 04 01 10 01 54 7b 65
Command: fa 00 04 01 10 01 50 77 61
Command: fa 00 04 01 10 01 4c 73 5d
Command: fa 00 04 01 10 01 47 6e 58
Command: fa 00 04 01 10 01 43 6a 54
Command: fa 00 04 01 10 01 3d 64 4e
Command: fa 00 04 01 10 01 35 5c 46
Command: fa 00 04 01 10 01 32 59 43
Command: fa 00 04 01 10 01 2e 55 3f
Command: fa 00 04 01 10 01 2a 51 3b
Command: fa 00 04 01 10 01 27 4e 38
Command: fa 00 04 01 10 01 24 4b 35
Command: fa 00 04 01 10 01 1f 46 30
Command: fa 00 04 01 10 01 1b 42 2c
Command: fa 00 04 01 10 01 18 3f 29
Command: fa 00 04 01 10 01 16 3d 27
Command: fa 00 04 01 10 01 10 37 21
Command: fa 00 04 01 10 01 0e 35 1f
Command: fa 00 04 01 10 01 0c 33 1d
Command: fa 00 04 01 10 01 08 2f 19
Command: fa 00 04 01 10 01 05 2c 16
Command: fa 00 04 01 10 01 02 29 13
Command: fa 00 04 01 10 01 00 27 11
Command: fa 00 04 01 10 01 02 29 13
Command: fa 00 04 01 10 01 07 2e 18
Command: fa 00 04 01 10 01 0c 33 1d
Command: fa 00 04 01 10 01 10 37 21
Command: fa 00 04 01 10 01 1a 41 2b
Command: fa 00 04 01 10 01 1f 46 30
Command: fa 00 04 01 10 01 25 4c 36
Command: fa 00 04 01 10 01 2a 51 3b
Command: fa 00 04 01 10 01 35 5c 46
Command: fa 00 04 01 10 01 3b 62 4c
Command: fa 00 04 01 10 01 40 67 51
Command: fa 00 04 01 10 01 44 6b 55
Command: fa 00 04 01 10 01 4e 75 5f
Command: fa 00 04 01 10 01 53 7a 64
Command: fa 00 04 01 10 01 5d 84 6e
Command: fa 00 04 01 10 01 62 89 73
Command: fa 00 04 01 10 01 68 8f 79
Command: fa 00 04 01 10 01 70 97 81
Command: fa 00 04 01 10 01 77 9e 88
Command: fa 00 04 01 10 01 7d a4 8e
Command: fa 00 04 01 10 01 82 a9 93
Command: fa 00 04 01 10 01 8e b5 9f
Command: fa 00 04 01 10 01 93 ba a4
Command: fa 00 04 01 10 01 9d c4 ae
Command: fa 00 04 01 10 01 a0 c7 b1
Command: fa 00 04 01 10 01 a4 cb b5
Command: fa 00 04 01 10 01 ac d3 bd
Command: fa 00 04 01 10 01 af d6 c0
Command: fa 00 04 01 10 01 b2 d9 c3
Command: fa 00 04 01 10 01 b5 dc c6
Command: fa 00 04 01 10 01 bc e3 cd
Command: fa 00 04 01 10 01 bf e6 d0
Command: fa 00 04 01 10 01 c2 e9 d3
Command: fa 00 04 01 10 01 c6 ed d7
Command: fa 00 04 01 10 01 cb f2 dc
Command: fa 00 04 01 10 01 cf f6 e0
Command: fa 00 04 01 10 01 d9 01 ea
Command: fa 00 04 01 10 01 e0 08 f1
Command: fa 00 04 01 10 01 e6 0e f7
Command: fa 00 04 01 10 01 f2 1a 04
Command: fa 00 04 01 10 01 f7 1f 09
Command: fa 00 04 01 10 01 fd 25 0f
Command: fa 00 04 01 10 01 ff 27 11
