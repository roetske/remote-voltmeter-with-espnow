# remote-voltmeter-with-espnow 
![image](https://github.com/user-attachments/assets/52304627-868e-4aef-a64e-d8dc5ba9e61f)
# purpose
Remote monitoring of 2 voltages.<br />
The advantage the communication between the 2 modules is via wifi direct via espnow.<br />
Before for wireless connections you need to connect to existing wifi and then interconnect. With espnow you can connect without router.<br />
Connect two voltages between 0-30v with module2. Monitor the 2 voltages remotely on module1.<br />
Connection is based on macaddress of both esp32 declared in the code.<br />
Library espnow espressif allows you to make direct connection between esp32<br />

# module1
esp32 with external antennae<br />
oled 0.96 displays the 2 voltages<br />
Blueled blinking when connection active with module 2<br />
The results of the measurements on module2 are displayed on oled of module1.<br />
Power via micro c cable or 5v external supply.<br />
# module2 
esp32 with external antennae relays measured voltages to module1 via espnow<br />
2 ina219 measure voltages connection i2c<br />
2voltmeters are also mounted to visually show voltages<br />
blue led blinks when active connection with other module<br />
power from one channel is used to power via buckconverter the esp32<br />
however if you want to use external power => power via the micro c connector on esp32 and external 5v powerbank<br />
# remarks
Very important you need the macadress of both esp32 and implement in to your code to get it working!!! <br />
The esp32 mac is specific for your esp32. If you replace the esp32 with another you have to change the mac  <br />
accordingly in the code!!! <br />
My first setup worked but failed after a while. Both ina219 where broken. <br />
I changed the setup of measuring by using a voltage divider and a zener diode to limit the input voltage to the ina219 's.<br />
For the espnow i used channel 4. This is fix but you can change it in the code.<br />
I also planted a watchdog in both module so when one hangs it is automatically restarts.<br />
Now the working is good and quite fast. Sample time is 0.5s.<br />






