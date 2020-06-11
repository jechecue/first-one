# Fixing cheap Wi-Fi repeater
## Introduction
As it usually happens to a lot of people,  I needed to install  Wi-Fi repeaters to reach those points in my house with poor coverage from my Router. Some time ago I bought a couple of cheap Wi-Fi repeaters from a well-known Chinese online shop. It is a very common model tha can be found in other shops. I give you a pair of links:

- <a href="https://es.aliexpress.com/item/32951118473.html">Aliexpress</a>
- <a href="https://www.amazon.es/Amplificador-Repetidor-Extensor-inal%C3%A1mbrico-integradas/dp/B082D5VHPT">Amazon</a>

The installation and start up is very easy and I was very happy with them until one of them started to fail. Initially the communication was interrupted until a moment came when it no longer worked. I thought that the device had lost its configuration but, after doing a reset, the Wi-Fi point that allows you to configure it did not appear, nor did it respond through the Ethernet network connection.

As I had several, I replaced the device with another one and stored the breakdown in case it was useful in the future. After a while, the other one also started to fail and this is something that already alerted my maker sense.

## Fault-finding process
The first thing to say is that when I opened the device I did not intend to fix it. I don't have the patience or the time. As I am very practical, comparing the cost of the device with the cost of my time it is quite possible that it is cheaper to buy another one than to fix it.

However, satisfying one's curiosity, learning something else, is something that also has its value. Perhaps the failure was due to poor electrical installation, storm problems or simply a faulty production batch. In any case, I thought I had to find out the cause of the failure of the devices because it didn't make much sense to buy more if they were really going to fail.

The first step was to open the device. I realize that there were two modules:

 - One with a pair of wires connected to the AC terminals and with other pair connected to the second module. That usually means that it is the power supply. 
 - The other was a single PCB board including the RJ45 Ethernet connector, some SMD LEDs and switches. Clearty it was the main Wi-Fi module.

The second step was to check if the power supply was working properly. I checked with a multimeter if there were power at the AC input terminals in the PCB and it was OK. Then, I checked the output terminals connected to the Wi-Fi module. I saw in the PCB a pair of labels with a "+" and a "-", confirming that the output was DC, so I used the multimeter in DC Volts mode. There was no output voltage.

At this point it was clear that the problem was in the power supply module. Checking the second device confirmed my first impression. But I had to hold my horses becouse sometimes the power supply can be damaged afther the load it powers (the Wi-Fi module in this case) is damaged and produces an overload of the power supply. Or, conversely, a failure in the power supply module can ruin the element it feeds. There were no damaged components at the power supply module but this is not always definitive.

To check if the Wi-Fi module worked, I planned to use my home-made lab power supply. It can provide 0-30 V and shows the current it provides to the load.  As none of the power supply modules were working and there was no information about the voltage they provide it were going to be an "interesting" enquiry. After taking a look to the components of the module and their datasheet it seemed they were working at 3.3 V but this information was not the last word. 

So, I decided to use my power supply starting to feed the module with 3.3 volts and see what happened. Then, was when the fun started.
- Using 3.3 V the module didn't show any change (the power LED didn't light up). The consumption showed by my power supply was 1 A. Perhaps, it needed a higher voltage.
- Using 5 V showed the same but the current was 1.6 A. Ok, let's increase the voltage to the next level
- Using 9 V I got the same state but this time the circuit started to smell of burning and smoke started coming out of one part of the circuit. Ok, time to switch off quickly the power supply.


## Fixing the device


