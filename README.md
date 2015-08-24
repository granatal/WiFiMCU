
# **WiFiMCU** #
   WiFiMCU is developed based on EMW3165 module produced by Mxchip.inc. A Lua interpreter is builded inside with hardware support. A light weight file system and socket protocols can help to realize IoT development easily and quickly. Basically, you can load this on your device and then run Lua scripts on it with nothing more than a terminal connection. Enjoy it!

#####Cortex-M4 microcotroller<br/>
- STM32F411CE<br/>
- 100MHz,Cortex-M4 core<br/>
- 2M bytes of SPI flash and 512K bytes of on-chip flash<br/>
- 128K bytes of RAM<br/>
- Operation Temperature：-30℃ ~ +85℃<br/>

#####Multi-Interface<br/>
- 17 GPIO Pin<br/>
- 3 UARTs<br/>
- ADC(5)/SPI(1)/I2C(1)/USB(1)<br/>
- SWD debug interface<br/>
- 11 PWMs<br/>

#####Broadcom IEEE 802.11 b/g/n RF Chip<br/>
- Supports 802.11 b/g/n<br/>
- WEP,WPA/WPA2,PSK/Enterprise<br/>
- 16.5dBm@11b,14.5dBm@11g,13.5dBm@11n<br/>
- Receiver sensitivity：-87 dBm<br/>
- Station,Soft AP and Station+Soft AP<br/>
- CE, FCC suitable<br/>

#GPIO table

#Program demos
####Setup a AP

```lua
    cfg={ssid='Doit_3165',pwd=''}
    wifi.startap(cfg)
```
####WebServer

```lua
   skt = net.new(net.TCP,net.SERVER) 
   net.on(skt,"accept",function(clt,ip,port) 
   print("accept ip:"..ip.." port:"..port.." clt:"..clt) 
   net.send(clt,[[HTTP/1.1 200 OK
   Server: WiFiMCU
   Content-Type:text/html
   Content-Length: 28
   Connection: close
   
   
   <h1>Welcome to WiFiMCU!</h1>]])
   end)
   net.start(skt,80) 
```


###The IDE tool for wifimcu can be found here
https://github.com/SmartArduino/WiFiMCU-STUDIO

####Acknowledgements
Thanks to [eLua project](https://github.com/elua/elua),[NodeMCU project](https://github.com/nodemcu/nodemcu-firmware),[spiffs file system](https://github.com/pellepl/spiffs)<br/>

####More information please go to
www.wifimcu.com<br/>

####[Doctors of Intelligence & Technology](www.doit.am)
[WiFiMCU Dev Kit](http://www.smartarduino.com)

####Version log
v0.9.4@2015-8-24<br/>
repair wifi module bugs<br/>
v0.9.3@2015-8-18<br/>
change the bootloader ymodem.c<br/>
v0.9.2@2015-8-15<br/>
add uart/pwm/adc modules change<br/>
change net module<br/>
change the logo<br/>
v0.9.1@2015-7-26<br/>
initial publish<br/>
