# Motor board protocol

---

## Serial Parameters
- **Baudrate**: 57600

## Command Decode
- **Header**: `fa 00`

---

## List of Commands

### Power Control
- **Power On**: 
  ```
  fa 00 02 4f 7f 0b cb
  ```
- **Power Off**: 
  ```
  fa 00 02 4f 8b 4c
  ```

### Version ID
- **Get Version ID**: 
  ```
  fa 00 01 56 44 52
  ```
  - _Tablet Reports_: MCB is running firmware version: `[2.390000]`

### Calibration Values
- **Calibration Values**: 
  ```
  fa 00 01 42 30 3e
  ```
  - _Returns values in the tablet. ToDo: Check those values._

### Read Values
- **Read VR Values**: 
  ```
  fa 00 01 40 2e 3c
  ```
  - _Tablet returns status (position maybe?) of all 7 motors._
  
- **Read PID Values**: 
  ```
  fa 00 01 47 35 43
  ```
  - _Tablet returns PID values._

### Reset and Test Commands
- **Reset PID Values**: 
  ```
  # ToDo: Check command for resetting PID values.
  ```

- **Slow Blink**: 
  ```
  fa 00 0f 01 60 84 16 16 14 fc fc 3c 0b 0b 3c 16 16 0a bf ee
  ```
  
- **Single Cycle Test** (Moves eyes up and down): 
  ```
  fa 00 07 01 08 04 e5 7f 19 7f 19 0d
  ```

- **Double Cycle Test** (Moves eyes up and down 5 times): 
  ```
  fa 00 0b 01 08 08 e5 7f 19 7f e5 7f 19 7f 69 13
  ```

- **5 Cycle Test** (Moves eyes up and down 5 times): 
  ```
  fa 00 17 01 08 14 e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f e5 7f 19 7f ab 25
  ```

## Calibration Commands
- **CAL LDL** (Calibrate Left Eyelid): 
  ```
  fa 00 02 43 40 b3 80
  ```
  
- **CAL LDR** (Calibrate Right Eyelid): 
  ```
  fa 00 02 43 20 93 60
  ```

- **CAL ELR** (Calibrate Horizontal Eye Movements): 
  ```
  fa 00 02 43 10 83 50
  ```

- **CAL EUD** (Calibrate Vertical Eye Movement): 
  ```
  fa 00 02 43 08 7b 48
  ```

- **CAL NE** (Calibrate Vertical Head Movement): 
  ```
  fa 00 02 43 04 77 44
  ```

- **CAL NR** (Calibrate Horizontal Head Movement): 
  ```
  fa 00 02 43 02 75 42
  ```

- **CAL NT** (Calibrate Head Tilt): 
  ```
  fa 00 02 43 01 74 41
  ```

## Movement Test Commands
#### Eyelid Movements
- **LDL Left Eyelid**: 
  - Scroll Right (Close): 
    ```
    fa 00 04 01 40 01 ff b7 41
    ```
  
  - Scroll Left (Open): 
    ```
    fa 00 04 01 40 01 00 b7 41
    ```

- **LDR Right Eyelid**: 
  - Scroll Right (Close): 
    ```
    fa 00 04 01 20 01 ff 57 21
    ```
  
  - Scroll Left (Open): 
    ```
    fa 00 04 01 20 01 00 57 21
    ```

#### Eye Movement
- **ELR Horizontal Eye Movement**: 
  - Scroll Right (Eyes to the Right): 
    ```
    fa 00 04 01 10 01 ff 27 11
    ```
  
  - Scroll Left (Eyes to the Left): 
    ```
    fa 00 04 01 10 01 00 27 11
    ```

- **EUD Vertical Eye Movement**: 
  - Scroll Right (Eyes Looking Down): 
    ```
    fa 00 04 01 08 01 ff 0f 09
    ```
  
  - Scroll Left (Eyes Looking Up): 
    ```
    fa 00 04 01 08 01 00 0f 09
    ```

#### Head Movement
- **NE Vertical Head Movement**: 
  - Scroll Right (Head Up): 
    ```
    fa 00 04 01 04 01 ff 03 05
    ```
  
  - Scroll Left (Head Down): 
    ```
    fa 00 04 01 04 01 00 03 05
    ```

- **NR Horizontal Head Movement**: 
  - Scroll Right (Head Moves to the Left): 
    ```
    fa 00 04 01 02 01 ff fc 03
    ```
  
  - Scroll Left (Head Moves to the Right): 
    ```
    fa 00 04 01 02 01 00 fc 03
    ```

- **NT Head Tilt**: 
  - Scroll Right (Head Tilts to the Left): 
    ```
    fa 00 04 01 01 01 ff f9 02
    ```
  
  - Scroll Left (Head Tilts to the Right): 
    ```
    fa 00 04 01 01 01 00 f9 02
    ```
