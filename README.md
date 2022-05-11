# Automotive-Hacking-ComSec
Research into Automotive Hacking for the ComSec (Computer Science) society with a PowerPoint presentation and simulator to show these attacks in action. This includes but not limited to capturing CAN (Controller Area Network) packets and relaying them to a car. This can be done by finding the ID for reving a cars engine by monitoring the cars packets via wireshark or specified scripts and seeing the rev counter increase then capturing this output. The captured output(rev packets) are then re-sent showing the car to rev, turn, signal ect.

### `---Disclaimer---`
I am using a third parties repository for the simulator

## Team Members 

|   Name              |    Username     |
|---------------------|-----------------|
| Owen Ball           |   Ballo-02      |

## What's in this repository?
### `Automotive_Hacking`
The presentation showing the rsearch and tasks (with answers) for the simulator

### `Guide.txt`
commands and setup for the simulator as shown below

## Official Documentation of the simulator

`Setup`

- git clone https://github.com/zombieCraig/ICSim
- sudo apt-get install libsdl2-dev libsdl2-image-dev –y
- sudo apt-get install can-utils -y
- cd ICSim
- make
- ./setup_vcan.sh


`Check if working`

- Ifconfig vcan0

`Run Simulation`

- ./icsim vcan0 = speedometer
- ./controls vcan0 = controls

`Controls`

- Accerlate = Up Arrow
- Left/Right Turn signal = left/right arrows
- Unlock Front left/right doors = right-shift +A, right-shift +B
- Unlock Back left/Right = right-shift+X, right-shift+Y
- Lock All Doors = Hold right shift key, Tap left shift
- Unlock all doors = Hold left shift key, Tap right shift 


`Commands`

- cangen vcan0 = send CAN packet
- candump vcan0 = dump live can files on vcan0
- candump -I vcan0 = dumps the can packets live into a file until ctrl_C pressed
- cansniffer -c vcan0 = live feed of can packets with highlighted changes 
- press -0000 +enter, +ID to view specific ID CAN information
- canplayer -I canfile.log = replay CAN packets via file
- wc -l canfile.log = vuew amount of CAN commands sent
- split -l "1/2 CAN total" canfile.log name = splits the file into half and replays that


`Extra Material`

https://medium.com/@yogeshojha/car-hacking-101-practical-guide-to-exploiting-can-bus-using-instrument-cluster-simulator-part-i-cd88d3eb4a53
