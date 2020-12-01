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
	