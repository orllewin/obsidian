Our water comes from a brick tank buried in Todmorden Moor, we added a filter in 2017 when S was pregnant with A, a good addition now rain water is considered [unsafe to drink globally](https://www.vice.com/en/article/m7gban/rainwater-everywhere-now-considered-too-toxic-for-safe-consumption-study-finds). The overflow from our tank feeds two large black plastic tanks downstream for our neighbours at Ridge House and also in the converted pub next to us.

In August 2022 the water level in the tank was very low, prompting us to conserve water by not taking baths and flushing less. Ridge House had run out entirely and was bringing water to their property in large tanks on a trailer. 

I wanted to build something so we didn't have to head up onto the moor to check the levels. Initially I thought of a [Raspberry Pi Zero](https://thepihut.com/products/raspberry-pi-zero-w) with an [ultrasonic sensor](https://shop.pimoroni.com/products/ultrasonic-distance-sensor)  and a [LoRa](https://en.wikipedia.org/wiki/LoRa) hat, mainly because I've used the Pi Zero a lot already and have a few lying around, but after some research it was clear that they use far too much power and aren't suited to the project. I did think about maybe the [Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) or an [ESP32](https://en.wikipedia.org/wiki/ESP32) (again, I have a few from old projects), whatever I intended to build would need a small solar panel, a [Lipo solar charger](https://thepihut.com/products/solar-lipo-charger-3-7v), battery, and a lot of tinkering and development but then I remembered a local project from when the valley flooded for monitoring river levels and reached out to someone I vaguley remembered was involved: [Bridge Rectifier](http://bridgerectifier.org.uk).

I got a fantastic email back from Andrew with links from the project:
* [flood.network/](https://flood.network/)
* [wiki.thingscalderdale.com/Main_Page](https://wiki.thingscalderdale.com/Main_Page)

Andrew also sent me this link to a LoRa sensor that does everything I need: [LDDS75-8 LoRaWAN Distance Detection Sensor](https://www.ukiot.store/product/ldds75-lorawan-distance-detection-sensor/). Using this (together with a [gateway that doubles as a server](https://www.ukiot.store/product/lps8v2-indoor-lorawan-gateway/)) would cost more than a homegrown solution but it would also take much less time and be more reliable with less maintenance, it has a 10 year battery so no solar setup needed. 

The above sensor and gateway is on order - I'll update this when it arrives and I set it all up.

