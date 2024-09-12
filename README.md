# I-made-200Watt-Class-D-amplifier
Class D TPA3221 based Fully Assembled Amplifier board, It can output a max of 200W RMS on 2ohm load. The design is minimal and small.
Get the full project details on: https://www.pcbway.com/project/shareproject/I_made_200Watt_Class_D_amplifier_d9f40c31.html

![thumb](https://github.com/user-attachments/assets/f524308f-daae-4673-9e8d-17e9bdba5361)

I have designed this 200W Class D amplifier board, which is separated into 100+100 Watt stereo channels. I went for TPA3221 for its great features, listed below. Moreover this audio amplifier can be used with bookshelf speakers and in home theater systems. The amplifier is capable of generating 170W power at 1% total harmonic distortion with 2 ohm speaker load in PBTL configuration. The board has selectable gains which can be altered by using different resistors settings, but for this design I adopted a max gain of 30dB.

![mini_IMG_6881](https://github.com/user-attachments/assets/659d4753-441d-42cf-9a96-34bf23030fcd)

The amplifier can be supplied with a 7-30V power supply, but I will recommend using at least 24V 10A SMPS with this. The best feature of Class D amplifiers I have found is low heat dissipation, high efficiency and these amplifiers do not need dual rail power supplies, so the power supply section is easy to design. This project is sponsored by PCBWAY, China based PCB manufacturer having 10 years of experience in working with PCB related products. PCBWAY is a one stop solution to all your prototyping requirements including SMT assembly, Stencil, 3d printing and metal CNC.

Features of TPA3221 IC:

![2020_0501_164827_004](https://github.com/user-attachments/assets/2d62928b-eb6d-4a1b-a7d3-02c851c56638)

Wide 7-V to 30-V Supply Voltage Operation

Stereo (2 x BTL) and Mono (1 x PBTL) Operation Low-Power Operating Modes

Standby Modes: Mute and < 1 mA Shutdown, Low Idle-Current HEAD Modulation

Multiple Input Options to Simplify Preamp Design

Differential or Single-Ended Analog Inputs

Selectable Gains: 18 dB, 24 dB, 30 dB, 34 dB

Integrated Protection: Undervoltage, Overvoltage,Short Circuit, Clipping Detection, Over Temperature Warning and Shutdown.

Inbuilt DC Speaker Protection

90% Efficient Class-D Operation (4 Ω)

Circuit Diagram:

![Screenshot_2024_09_10-1](https://github.com/user-attachments/assets/7fc0f08b-81bd-46ea-b9ba-aa0ca5e15b0e)

I have taken the reference directly from the TI datasheet, usually TI engineers post an application circuit with calculated values at the end of the datasheet with PCB layout design. In this way anyone with good electronics skill can design the circuit by following the notes and precautions. For some features we have to read the entire datasheet and sometimes may have to calculate the values as per desired response. So I modified the circuit according to my design specifications. And the finalized circuit is attached below.

![Schematic_tpa3221-Class-D_2024-08-22](https://github.com/user-attachments/assets/73c3adbc-c636-4b1c-a8b7-c23f3bb96763)

The updated schematics is divided into different sections as per usage, Power filters to decay down power supply input noises. Then the main amplifier which contains all the main gain and mode settings. Then reset and mute section, to avoid power on noise we have to turn off reset button after powering. To mute the device when it is operating at full potential mute switch can be turned on. Then the main output section contains signal filters, which turn the Class D PWM signal into analog output. And the final section contains I/O pins.

PCB Design:

![Screenshot_2024_06_21-3](https://github.com/user-attachments/assets/0cfb9293-3c99-4dd2-bc21-6219a7259f3f)

The board is designed on a 4 Layer PCB stackup to minimize the noise and any humming in the circuit ground plane is used underneath the main signal layer. The proper stackup of the PCB is defined as Signal/GND/5V/Signal. The output section is routed away from the input section so that any backpropagation and signal crossover do not happen in the PCB. As per datasheet the decoupling capacitors are used near to main IC, near to power pins so any noise in the input power supply signal can be eliminated. I used the PCBWAY SMT assembly process to get the soldering and part placement done easily.

![Screenshot_2024_07_05-1](https://github.com/user-attachments/assets/6c75ce6d-867b-480c-a785-4c5d31fe64e3)

To route the main input audio signal 50 ohm line is used on the signal layer and to route the output section polygon planes are used. Vias at different points in signal and power planes are avoided to reduce the noise. The best practice to route the output section with via’s is to use different via’s with the same track in this way the current is distributed in the different tracks and propagation of signal is possible easily. I have stitched the signal layer copper pour with the ground plane to reduce the EMI problems in the circuit. Download all the design files from here.

Connection and Power ON:
Two slide switches can be seen on the top layer of the board. One is to reset the IC, and one is used as a mute switch. Reset can be turned off after powering the IC, in this way any glitches in the output can be eliminated. CMute switches are connected to a MOSFET which is controlling the Mute pin of the IC, this is used to power off the amplifier from active output mode.

![mini_IMG_6963](https://github.com/user-attachments/assets/1240ea44-1ec0-4a92-9d51-407bd1d52c98)

For the power input, two different isolated supplies can be externally connected to the amplifier. One to provide the logic 5 volt signal to the amplifier to turn on the logic function of the amplifier and a 30V supply as the main power supply unit, ground will remain the common for both.

![mini_IMG_6966](https://github.com/user-attachments/assets/25c353c5-0212-4dc6-b275-2711df4bb247)

For audio input signals from any audio source like bluetooth, Mobile/Laptop Aux or from DSP can be given to the amplifier. A max of 5v peak to peak can be fed for the maximum signal output. I will recommend using a preamplifier which also opens up the options of frequency controlling like bass and treble.

Working and Testing:

![mini_IMG_6964](https://github.com/user-attachments/assets/d2138558-7d29-4050-9a4a-23c08680f214)

Here I have attached a video, here you can see the raw audio performance. The testing setup includes a DSP unit, 24V 10A power supply and 200W subwoofer. Test at 70% volume the amplifier performs best and produces very low heat which can be dissipated by a 40x30mm passive heat sink.

Final words:

![mini_IMG_6955](https://github.com/user-attachments/assets/64064cf5-8aa4-4220-a70d-712b1d9068fd)

The audio performance of the amplifier is quite good, not having any problems of noise or hum at the power ON. The filter section is well designed to convert the PWM to analog audio signal. Overall the amplifier performs well, as tested out with the custom made  DSP and preamplifier unit. The highs, mid and low bass frequency is clear as used with the tweeter, subwoofer and woofer. Some distortion in the voice clarity can be seen at max volume output of the amplifier in the medium frequency range. 

![Screenshot_2024_09_13-1](https://github.com/user-attachments/assets/a37941bd-e16b-4158-a898-e16d25a30c35)

Try the best PCB services now and turn your dream projects into real world applications with PCBWAY.  Explore the new PCB DESIGN CONTEST launched by PCBWAY recently.
