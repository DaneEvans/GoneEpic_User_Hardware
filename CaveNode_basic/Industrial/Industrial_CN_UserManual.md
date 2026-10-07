# Industrial CaveNode - User Manual
Revision 1.0 

## General Usage 
In General, we use the Meshtastic apps, the firmware is designed to utilise the open source apps.
The Nodes are equipped with a short range bluetooth antenna, ~3 m but may be impacted by other bluetooth devices or shielded boxes.

Download the app for your phone ecosystem.

### Pairing to a phone (BT)
- Initiate pairing through the App
- The default passcode is 123456
- If you have multiple devices in proximity, use the device ID engraved on the device to ensure you are connected to the right one. 

## Indicator Lights
From Left (USB) to Right
- Charge  
- Activity 
- Admin controlled
- Range test 

## Installation
The CaveNode should be positioned so the glands and vent are placed to the bottom where possible to reduce the possibility of water ingress.
The vent will allow pressure equalisation without allowing water in.  

### Mounting
The Industrial CaveNodes have a removable mounting plate to enable easy placement. The bolt pattern is available in the drawing. 
[Drawing here](CN basic Mount Bracket drawing.pdf)

The Environmental sensor has two blind m3 nuts, at a 25mm spacing, which can be used to mount it to a variety of placements. 
[Drawing here](../../peripherals/Sensors/SCD41_CO2/Enviro Sensor housing Drawing.pdf)

### Hard Wiring - AC 240V
- requires 2 core AC wiring, diameter 3-6.5mm 
The AC cable should enter the right Gland, and be wired into the crimp.
Active Orange, Neutral Blue
Once this has been done, tighten the gland to create a waterproof seal 

### Battery
The battery is shipped disconnected, use tweezers or needle nose pliers to plug the battery in to the circuit board.
*note* the connector is keyed, and will only fit in one orientation.  

### Enclosure 
The lid can then be attatched, use a star pattern to seal the lid, snugging them down, before tensioning to xxNM 


## Additional sensors - Optional 
*If equipped* 
- I2C sensors can be attatched using the left cable gland if provisioned. 
- By default the sensor is equipped with a 4 pin Julet connector
- Sensor compatability depends on the Meshtastic version base,  

Compatible sensors 
- SCD41, SCD42, SCD43


## Updating Firmware
- Plug the Node into a PC (Or phone) using a USBC cable. (A USBA to USBC cable is more likely to work )
- Download a firmware file from [https://github.com/DaneEvans/Flamingo-Firmware/releases] - preferably the latest release
    - Use the -Flamingo variant for cave firmware
- Place in DFU mode using one of the following:
    1) Go to the Meshtastic Flasher: [https://flasher.meshtastic.org/]
        - Select Target - Rak4631
        - select any firmware (we won't use it anyway)
        - Press 'Flash'
        - Press the button to 'Enter DFU mode'
    2) Use a *non-conductive* probe to double click the reset button (next to the USB connector)
- The Node will reboot into DFU mode, and appear as a portable drive in wWindows Explorer / Finder
- Copy the firmware file to it. 
- await reboot. 


## Flamingo vs Meshtastic
The Flamingo variant is designed for underground use - it has a substantially higher hop count. 
The two are based on the same protocol, but are not compatible (On LoRa, UDP / MQTT may be)

To identify between the two 
- On Android - Open the Current Node on the Nodes page, under the Firmware > Firmware Edition section, it will show DIY_EDITION, rather than VANILLA
- Flamingo has a soft rangetest supression function and will respond to admin messages
- setting a hop limit > 7, using the CLI, it will stick on the Flamingo variant 
