# Packet-sniffer
A Network Packet Sniffer developed in Python 3. Packets are disassembled
as they arrive at a given network interface controller and their information
is displayed on the screen.


## Running the Application
### I. Development Mode
Simply clone this repository with `git clone`, install the dependencies and execute the 
`sniffer.py` file.
```
user@host:~$ git clone https://github.com/EONRaider/Packet-Sniffer.git
user@host:~$ cd Packet-Sniffer
user@host:~/packet-sniffer$ pip install -r requirements.txt <--or--> poetry install
user@host:~/packet-sniffer$ sudo python3 packet_sniffer/sniffer.py
```

*The `sudo` command is required due to the use of `socket.SOCK_RAW`,
which needs administrative privileges to run on GNU/Linux. Notice
that the existence of dependencies may require the execution of the interpreter contained in
the virtual environment in which the dependencies have been installed (if you use one),
instead of just using the system interpreter.*

### II. (Optional) Build the binary
Use the `build.py` file to compile your own binary with the `PyInstaller` package. You just need to install all dependencies and build. 
Dependency management works with both [Poetry](https://python-poetry.org/) (recommended) and [Virtualenv](https://virtualenv.pypa.io/en/latest/). 
```
<-- Install dependencies as shown above in Step I -->
user@host:~/packet-sniffer$ python3 build.py
```

## Usage
```
sniffer.py [-h] [-i INTERFACE] [-d]

Network Packet Sniffer

optional arguments:
  -h, --help            show this help message and exit
  -i INTERFACE, --interface INTERFACE
                        Interface from which packets will be captured (monitors
                        all available interfaces by default).
  -d, --data            Output packet data during capture.
```

