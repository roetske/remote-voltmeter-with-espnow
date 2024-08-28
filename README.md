# remote-voltmeter-with-espnow !!!work in progress!!!
# purpose
Connect two voltages between 0-30v with module2. Monitor the 2 voltages remotely on module1.<br />
I work a lot with robots.Power to io modules on grippers on robots have a bus system and<br />
2 supply voltages of 24V. <br />
One Voltage is permanent the other is on when the drives are on (supply power to outputs). When the powercable on the robot starts failing.<br />
It is hard to determine if it is the io module is failing,bus or the powersupply of 24V.<br />
With this setup you can connect the monitoring to these 2 voltages before the io module on the robot. <br />
Start your installation and have a realtimemonitoring of these 2 voltages. :)<br />
# modules
I made 2 modules.<br />
# module1
esp32 with external antennae<br />
oled 0.96 displays the 2 voltages<br />
blueled blinking when connection active with module 2<br />
# module2 
esp32 with external antennae relays measured voltages to module1 via espnow<br />
2 ina219 measure voltages connection i2c<br />
2voltmeters are also mounted to visually show voltages<br />
blue led blinks when active connection with other module<br />
power from one channel is used to power via buckconverter the esp32<br />
however if you want to use exteral power => power via the micro c connector on esp32 and external 5v powerbank<br />
# remarks
My first setup worked but failed after a while. Both ina219 where broken. 
I changed the setup of measureing by using a voltage divider and a zener diode to limit the input voltage to the ina219 's.
For the espnow i used channel 4. This is fix but you can change it in the code.
I also planted a watchdog in both module so when one hangs it is automatically restarts.
Now the working is good and quite fast. Sample time is 0.5s.





