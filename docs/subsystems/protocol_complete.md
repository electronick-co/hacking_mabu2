# Command list

| Method      | Description                          |
| :---------: | :----------------------------------: |
| [ON](#power-on)       | :material-cogs:     Turn on motor borad  |
| [OFF](#power-off)       | :material-cogs: Turn off motor board |
| [ON](#power-control)    | :information_source:     Delete resource |

# List of commands


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

## Part movement

| Command direction     | Header    | Payload    | CRC      | Comment                       |
| :-------------------: | :-------: | :--------: | :-----:  | :--------------------------:  |
| PC :arrow_right: Mabu | `fa 00`   | `04 01 ID 01 MV`| `C1 C2`  | |
| PC :arrow_left: Mabu  |    |  |  | See this section |

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
