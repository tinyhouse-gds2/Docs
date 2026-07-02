# Docs
primary technical documentation for the tinyhouse

# system-chart
```code

                       +--------+    +------+         |-------> | RP2040 |------------[nec]
                       |        |    | wifi |---------|            / \                 |
                       | Router | <--| mqtt |                       |                 \ /
                       |        |    +------+                       |               +-----+
                       |        |                      |----------- | ------------> | LED |
+-------+   +------+   |        |   +------+   +---+---+-+          |               +-----+
|       |<--| wifi |-- |        |<--| wifi |-- |         |          |  
|  RSP  | --| http |-->|        | --| http |-->|  Shelly |----(230V to 5V)
|       |   +------+   |        |   +------+   |         |          |      
+-------+              |        |              +---+---+-+          |               +-----+
                       |        |                      |----------- | ------------> | LED |
                       |        |                                   |               +-----+
                       |        |    +------+                       |                 / \
                       |        |    | wifi |                      \ /                 |
                       | Router | <--| mqtt |-----------------> | RP2040 |------------[nec]
                       |        |    +------+     
                       |        |                 
                       |        |   +------+   +---------+                           
                       |        |<--| wifi |-- |         |        +----------+                    
                       |        | --| http |-->|  Shelly | ------>| Radiator |   
                       |        |   +------+   |         |        +----------+                        
                       |        |              +---------+                           
                       |        |                                         
                       |        |                                         
                       |        |      +------+      +-------------+                   +------------+                                     
                       |        | <----| wifi |----- |  Yale       | --> |blue   | --> | Yale Linus |                          
                       |        |  ----| http |----->|  Wifibridge | <-- | tooth | <-- | Smartlock  |                       
                       |        |      +------+      +-------------+                   +------------+                  
                       |        |                                         
                       |        |                                         
                       +--------+                                         
                       
                                                   
                                                   
                                                   
                                                   
```

## Lichtsteuerung
[LostFlashlight/nec_over_wire](https://github.com/LostFlashlight/nec_over_wire)

## Server  
model: Raspberry Pi 5 8GB

## Administraition
can be ssh(ed) into when connectet to TinyNet or TinyNet2G
therefore use our computers Terminal and type  
```code
ssh tinypi@192.168.188.42
#and type in your Password
```
afterward you can use the UNIX/bash shell as you are use to
or switch to root with ```sudo su```


HAss ans all other services run in docker containers, there config is in 
```code
/opt/container-config
```
everything can be configured here, through ```yml``` files 
all though most things can be configured in the web-interface [Homeassistant-gui](http://192.168.188.42:8123) or the Homeassistant-App
that should be accessible through typing  ```http://192.168.188.42:8123```  into a browser (while being in TinyNet)
there you will have to login with your login credentials you will find those in the Keepass-Datebase.

## Router
to administrate the router you are going to need the [WinBox-App](https://flathub.org/en/apps/com.mikrotik.WinBox)
using this app you can log on to the Router while being in the Wifi-Network

## Temperature Sensors
The Temperature messuring assembly is implementend if from of two Sensors who are connected to one Raspberr Pi Pico W.
Which is spulied with power through USB and communicates over <Wifi <IP/TCP <MQTT> > >.
IT runs the follwing hadwrittenfireware: [Dual_DS18B20_Temp_Sensor](https://github.com/LostFlashlight/Dual_DS18B20_Temp_Sensor)

If you have any issues we are happy to help through the [issues panel](https://github.com/tinyhouse-gds2/Docs/issues).
