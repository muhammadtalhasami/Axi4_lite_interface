#  AXI4_LITE_INTERFACE

#  INTRO
Advanced eXtensible Interface 4 (AXI4) is a family of buses defined as part of the fourth generation of the ARM Advanced Microcontroler Bus Architectrue (AMBA) standard. AXI was first introduced with the third generation of AMBA, as AXI3, in 1996.

The AMBA specification defines 3 AXI4 protocols:

    AXI4: A high performance memory mapped data and address interface. Capable of Burst access to memory mapped devices.
    AXI4-Lite: A subset of AXI, lacking burst access capability. Has a simpler interface than the full AXI4 interface.
    AXI4-Stream: A fast unidirectional protocol for transfering data from master to slave.

Use in Xilinx-Based designs

Xilinx Vivado helps in the creation of custom IP with AXI4 interfaces. These can be connected to the Zynq’s Proccessing System or to other devices. This Document will cover the operation of the AXI4-Lite interface, which is convenient for implementing memory mapped registers.

# TRANSACTION AND CHANNELS

THere are two transactions Read and Wirte transaction

The AXI4-Lite interface consists of five channels: Read Address, Read Data, Write Address, Write Data, and Write Response. 

# AXI4 read transaction 
**1):** Read Address channel

**2):** Read Data channel 

# AXI4 write transaction 
**1):** Write Address channel

**2):** wite Data channel 

**3):** write Response channel

![axi4](https://github.com/muhammadtalhasami/Axi4_lite_interface/assets/141629485/188f4528-e291-4839-958a-a554c6564e19)


# HAND SHAKE PROCESS

All five transaction channels use the same VALID/READY handshake process to transfer address, data, and control information. This two-way flow control machanism means both the master and slave can control the rate at which the information moves between master and slave. The information source generates the VALID signal to indicate when the address, data or control information is available. The information destination generates the READY signal to indicate that it can accept the information. The handshake completes if both VALID and READY signals in a channel are asserted during a rising clock edge.


#  VIVADO_WAVEFORM
![Axi4_lite_interface](https://github.com/muhammadtalhasami/Axi4_lite_interface/assets/141629485/e1983157-c869-4561-b5e0-888914cb7026)

# VERILATOR_WAVEFORM
![WhatsApp Image 2024-05-02 at 8 40 30 PM](https://github.com/muhammadtalhasami/Axi4_lite_interface/assets/141629485/8351ce63-f4b5-4364-b332-377676eba8d6)

# SCHEMATIC VIEW
![axi4 schematic](https://github.com/muhammadtalhasami/Axi4_lite_interface/assets/141629485/bc58e6d9-abd5-4715-a82d-89783e7db706)

# HOW TO USE 

**1):** clone my repo
```
git clone https://github.com/muhammadtalhasami/Axi4_lite_interface
```
**2):** Follow this

For Vivado
```
https://github.com/muhammadtalhasami/Axi4_lite_interface/tree/main/AXI4_LITE_VIVADO/AXI4_LITE_INTERFACE.srcs

Here you will get the test bench and source code 
```


For verilator

Run make to compile the code and then run make waves to generate a wave form:
```
make

make waves
```

# RESOURCE

For more information on AXI4 Lite Protocol, https://www.realdigital.org/doc/a9fee931f7a172423e1ba73f66ca4081#introduction-to-axi4-lite-advanced-extensible-interface

# CONTRIBUTION

Contributions are welcome! Feel free to fork this repository, make improvements, and submit pull requests.
