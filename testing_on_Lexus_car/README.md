# Testing Apollo on Lexus Car

## General Information
Contains only some changed required modules from [official repo of Apollo](https://github.com/ApolloAuto/apollo)

## Dec 1st, 2020 Meeting
This meeting started with brief presentation about SocketCAN and how it works with AV car

- CAN bus driver
- SocketCAN
	- combination of CAN
	- implemented by Volkswagen Research
	- instead of IP map implementation, use CAN implementation
	- Code samples:
	
	```UNIX
	sudo modprobe can
	sudo modprobe can_raw
	sudo ip link set can0 type can bitrate 5000000
	sudo ip link set up can0
	```
- Other option: implmenting Kvaser client
	- Driver is ready
	- edit this configg file
- Set low-latency Linux

`sudo apt-get install -y linux-lowlatency`


## Reference(s)
- Credits to [Navid Bamdad Roshan](https://docs.google.com/document/d/19-NjgMJckhQ-rYFoHw4eI5fy8FPJ3ofTIzXevZ1Xh-0/edit?usp=sharing)