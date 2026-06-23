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
[github](https://github.com/LostFlashlight/nec_over_wire)

## Server  
model: Raspberry Pi 5 8GB

### Administraition
can be ssh(ed) into when connectet to TinyNet or TinyNet2G
therefore use our computers Terminal and type  
```code
ssh tinypi@192.168.188.42
#and type in your Password
```
afterward you can use the UNIX shell as you are use to

HAss ans all other services run in docker containers, there config is in 
```code
/opt/container-config
```
everything can be configured here, through ```yml``` files all though most things can be configured in the [HomeassistantGUI](192.168.188.42:8123)
that should be accessible through typing  ```192.168.188.42:8123```  into a browser (while being in Tiny Net)
there you will have to login with your login credentials you will find those in 
die smarte
