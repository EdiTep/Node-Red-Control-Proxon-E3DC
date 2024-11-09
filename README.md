# Control Proxon T300 hot water storage tank PV priority switching input with ShellyPlus1 via MQTT and Node-Red

## Overview of the project
Control of the PV priority switching input of the T300 hot water storage tank of a Proxon ventilation heating system using a ShellyPlus1 via Node-Red and MQTT.
The ShellyPlus1 is controlled via Node-Red and MQTT in such a way that the priority switching is activated when an adjustable battery charge and the feed-in reaches an adjustable wattage and deactivated again when the values are undershot.
A pushover message is sent on activation and deactivation so that the switching processes can be monitored even when nobody is at home.

On the circuit board of the T300, on which the display is also soldered, there is the terminal block X13. The circuit board is on the back of the display. To access the terminal block, you must first remove the long strip on the front below the display. It is only pressed into the side of the insulation of the device with pointed claws. There are three screws behind it that need to be loosened. You can then remove the entire upper part of the device insulation upwards. The display is inserted into two grooves and must be held firmly when sliding it out to prevent damage. The priority circuit of the PV system is located on terminal block X13. The switching input of the ShellyPlus1 is connected to X13-1 and X13-2. Please remember that this is a potential-free contact. The suitable relay in this case is the ShellyPlus1.
The control line can be led out of the T300 through an existing opening at the rear (this can be seen when you have removed the cover and the display) using a two-pole cable (I used a telephone cable). This cable have to bo connected with to the I/O connections of the Shelly 1 (note: only the ShellyPlus1 is potential-free!) and then evaluate all available parameters via the home automation system (battery charge status, current yield and thus switch the PV priority on or off. 

The terminal block X13 has 3.3 V at the connection itself. Following Parameters in the installer menu (code 1000) have to be adapted:

In the Installer menu:

    Set F22 PV mode to SG (Smart Grid). This activates the digital input
    Set F23 PV Eheiz to 5V
    Set F24 PV WP to 5V
    Set F25 WP Time to 5 min (or what you want, this is the time to wait bevor X13 switches to on)

In the Settings menu:

    D05 PV Priority ON

After I contacted Zimmermann, they sent me a CVS file with all the Modbus information, the wiring can be seen on the circuit diagrams that were given to me at the time of acceptance.
Please leave me an email via PM and I can send you the CSV file.


## Installation, requirements
1. Raspberry Pi is required as host for the other requirement
2. Install an MQTT Broker (i used Mosquitto)
3. Install Node-Red with Dashboard
4. Install RSCP to MQTT Dashboard v1.0
   - Download on Github here: https://github.com/pvtom/rscp2mqtt-dashboard
5. Install node-red-node-pushover - required to send Pushover Messages
   - a pushover account should be created, if you want to use it when the trial period ends, you have to pay $5. See Infos here: https://pushover.net/pricing
7. Configure ShellyPlus1 and integrate it into the network, so you can use it via MQTT
8. Connect the switching input of the Shelly to X13 1 + 2
    
## Node-Red Flow
The flow is available as a JSON file in the project and can be downloaded or the JSON code can be copied

## Documentation to set the T300 Parameters
A PDF-File with the Docu with screenshots is also available here in the project
