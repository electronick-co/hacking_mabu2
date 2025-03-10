# Motor board protocol

## Serial Parameters
- **Baudrate**: 57600

## Command list

| Command                                           | # bytes  | Description                          |
| :-----------------------------------------------: | :-------: |:----------------------------------: |
| [ON](#power-on)                                   |   7       |     Turn on motor BOARD  |
| [OFF](#power-off)                                 |   6       |     Turn off motor board |
| [VERSION ID](#version-id)                         |   6       |     Get the version ID of the board |
| [CALIBRATION](#calibration)                       |   7       |     Run calibration command |
| [GET CALIBRATION VALUES](#get-calibration-values) |   6       |     Get calibration values |
| [GET MOTOR POSITIONS](#get-motor-positions)       |   6       |     Get motor positions |
| [READ PID](#read-pid-values)                      |   6       |     Read stored PID values |
| [RESET PID](#reset-pid-values)                    |   X       |     Reset PID values |
| [PART MOVEMENT](#part-movement)                   |   9       |     Move specific motor to desired position |
| [CURRENT POSITION](#current-position)             |   14      |     Curent position message |
| [SLOW BLINK](#slow-blink)                         |   20      |     Do a slow blink routine |
| [SINGLE CCYLE TEST](#single-cycle-test)           |   12      |     Run cycle testing routine |
| [DOUBLE CYCLE TEST](#double-cycle-test)           |   16      |     Run cycle testing routine twice |
| [5 CYCLE TEST](#5-cycle-test)                     |   28      |     Run cycle testing routine 5 times |


## **Power On**

Power the motors ON. Without this command any move command will work.

| Command direction     | Header    | Payload    | CRC      |  Comment                      |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `02 4f 7f` | `0b cb`  | The command is always the same|
| PC :arrow_left: Mabu  | `fa 00`   | `02 4f 7f` | `0b cb`  | The answer is always the same | 


## **Power Off** 

Power the motors OFF.

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `02 4f`    | `8b 4c`  | The command is always the same|
| PC :arrow_left: Mabu  | `fa 00`   | `02 4f 00` | `8b 4c`  | The answer is always the same | 


## **Version ID** 

Returns the version ID of the board.

| Command direction     | Header    | Payload    | CRC      |
| :-------------------: | :-------: | :--------: | :-----:  |
| PC :arrow_right: Mabu | `fa 00`   | `01 56`    | `44 52`  | 
| PC :arrow_left: Mabu  | `fa 00`   | `05 56 F3 F2 F1 F0` | `C1 C2`  | 

`C1` and `C2` are the CRC value calculated.

`F3 F2 F1 F0` is the floating point number for the version (IEEE-754 Floating Point)

**Response example:** `fa 00 05 56 40 18 f5 c3 9e 68`. The version number is `40 18 f5 c3` which represent version 2.39


## **Calibration**

This command makes the selected part to move in the whole range.

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `02 43 ID`| `C1 C2`  |             |
| PC :arrow_left: Mabu  | `fa 00`   | `02 43 00` | `73 40`  | The answer is always the same for all parts |

`C1` and `C2` are the CRC value calculated.

`ID` is the id of the motor part:

| ID      | Part    | Descripton                  | Command                |
| :-----: | :-----: | :-----------:               | :-------------------:  |
| `01`    |    NT   | Head tilt                   | `fa 00 02 43 01 74 41`    |
| `02`    |    NR   | Head rotation               | `fa 00 02 43 02 75 42`    |
| `04`    |    NE   | Head Vertical movement      | `fa 00 02 43 04 77 44`    |
| `08`    |    EUD  | Eye Vertical movement       | `fa 00 02 43 08 7b 48`    |
| `10`    |    ELR  | Eye Horizontal movement     | `fa 00 02 43 10 83 50`    |
| `20`    |    LDR  | Right eyelid                | `fa 00 02 43 20 93 60`    |
| `40`    |    LDL  | Left eyelid                 | `fa 00 02 43 40 b3 80`    |

## **Get calibration values**

Returns the calibration values. 

ToDo -> Yet to be decoded

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `01 42`    | `30 3e`  |             |
| PC :arrow_left: Mabu  | `fa 00`   | `2b 42 3e 05 9b 0c 5d 07 16 05 88 0c 72 07 00 08 e4 08 e4 00 5f 03 de 04 7f 01 57 0a 1e 0d c7 02 d5 00 b9 0f e4 0e 6a 0a 2c 0d c2 02 fa da 41 80 00 00 3f 80 00 00 3a a3 d7 0a 3c 03 12 6f 3e 99 99 9a 3a 83 12 6f 3d a3 d7 0a 3f 00 00 00 3a 83 12 6f 3d a3 d7 0a` | `ce 9b`  | Need to be decoded |

## **Get motor positions**

Return the position of the motors.

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `01 40`| `2e 3c`  |             |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |

## **Read PID values**

Returns PID values

ToDo -> Yet to be decoded

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `01 47`    | `35 43`  |             |
| PC :arrow_left: Mabu  | `fa 00`   | `55 47 3f 4c cc cd 37 51 b7 17 41 00 00 00 3f 4c cc cd 37 51 b7 17 41 00 00 00 40 06 66 66 3b 16 bb 99 41 80 00 00 40 06 66 66 3b 16 bb 99 41 80 00 00 3f 80 00 00 3a a3 d7 0a 3c 03 12 6f 3e 99 99 9a 3a 83 12 6f 3d a3 d7 0a 3f 00 00 00 3a 83 12 6f 3d a3 d7 0a` | `ce 9b`  | Need to be decoded |

## **Reset PID values**

TBD


## **Part movement**

Command to move certain motor into a specified position

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `04 01 ID 01 MV`| `C1 C2`  | |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |

`C1` and `C2` are the CRC value calculated.

`MV` is the value of the movement, form 0x00 to 0xff

`ID` is the id of the motor part:

| ID      | Part    | Descripton                  | Command example         |
| :-----: | :-----: | :-----------:               | :-------------------:  |
| `01`    |    NT   | Head tilt                   | `fa 00 04 01 01 01 ff f9 02`    |
| `02`    |    NR   | Head rotation               | `fa 00 04 01 02 01 ff fc 03`    |
| `04`    |    NE   | Head Vertical movement      | `fa 00 04 01 04 01 ff 03 05`    |
| `08`    |    EUD  | Eye Vertical movement       | `fa 00 04 01 08 01 ff 0f 09`    |
| `10`    |    ELR  | Eye Horizontal movement     | `fa 00 04 01 10 01 ff 27 11`    |
| `20`    |    LDR  | Right eyelid                | `fa 00 04 01 20 01 ff 57 21`    |
| `40`    |    LDL  | Left eyelid                 | `fa 00 04 01 40 01 ff b7 41`    |

## **Current position**

This is a response from the [movement command](#part-movement) and the.

When the part movement command is sent, this response will repeat until achieving a stable status.
When the response id from the status command, it will only span once.

| Command direction     | Header    | Payload    | CRC      |
| :-------------------: | :-------: | :--------: | :-----:  |
| PC :arrow_left: Mabu | `fa 00`   | `09 01 00 P7 P6 P5 P4 P3 P2 P1`| `C1 C2`   |

`C1` and `C2` are the CRC value calculated.

`P#` is the position of such motor, from 0x00 to 0x0ff:

| Part      | Part    | Description                  | 
| :-----: | :-----: | :-----------:               | 
| `P1`    |    NT   | Head tilt                   | 
| `P2`    |    NR   | Head rotation               | 
| `P3`    |    NE   | Head Vertical movement      | 
| `P4`    |    EUD  | Eye Vertical movement       | 
| `P5`    |    ELR  | Eye Horizontal movement     | 
| `P6`    |    LDR  | Right eyelid                | 
| `P7`    |    LDL  | Left eyelid                 | 

Command example:  `fa 00 09 01 00 6e 78 7b 77 68 64 76 be 22`

## **Slow blink**

Do a slow blink. Decoding this will help to send a set of movements at the same time

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `0f 01 60 84 16 16 14 fc fc 3c 0b 0b 3c 16 16 0a`| `bf ee`  | |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |

## **Single cycle test**

Send a command that moves eyes up and down

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `07 01 08 04 e5 7f 19 7f`| `19 0d`  | |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |

## **Double cycle test**

Send the cycle test twice


| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `0b 01 08 08 e5 7f 19 7f e5 7f 19 7f`| `69 13`  | |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |


## **5 Cycle test**

Run the testing cycle 5 times

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `17 01 08 14 e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f`| `ab 25`  | |
| PC :arrow_left: Mabu  |    |  |  | [See this section](#current-position) |


