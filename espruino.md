!['Espruino Pico'](espruino.PNG?raw=true)

This is an Espruino Pico. It's a small USB microprocessor that has Javascript built into it. It is a tiny 84MHz computer with 384kb flash storage, and 96kb RAM. It's not much, but it is enough to do some fairly interesting things. It has GPIO pins that can interact with other electrical components like LEDs, buttons, switches, sensors, speakers etc. You can connect it to a wifi module and get it connected to a network and interacting with things over the internet or local network. This one doesn't have the wifi module built in, but [it's successor does.](http://www.espruino.com/WiFi) There's also the newest one: puck.js it has built-in Bluetooth along with NFC and a few other sensors.

# [Espruino setup and quickstart](http://www.espruino.com/Quick+Start)

This page will help you get the basics set up. I would recomend using the [chrome plugin IDE](https://chrome.google.com/webstore/detail/espruino-web-ide/bleoifhkdalbjfbobjackfdifdneehpo?hl=en) to start with. Once you get through the basic setup and toggling onboard LEDs, you can start to learn about the electrical circuit side.

# Breadboard Basics

The white board with all of the holes in it is a breadboard. This is kind of like a scratch-pad for making electrical circuits. You can think of each hole like an electrical plug. You plug in wires and other electrical components to build and test circuits. The holes are connected internally in a pattern that makes it easier for us to connect components together with each other and our main board. Here is how the internal connections look:
!['Bread Board'](breadboard_90.png?raw=true)

The lines of connected plugs are called rails. This picture has two full length rails on the top and bottom of the board. Your board only has 1 on each side, but it is still connected all the way down as depicted in this photo. The colors red and blue don't have strict significance. They are used to illustrate what people commonly use the side rails for, one to carry power, and the other ground. But there is nothing preventing you from using them for whatever else you might want.

The pico is connected to the breadboard like this:
!['Pico Bread Board'](pico_on_breadboard.PNG?raw=true)

So each pin on either side of the pico is connected to one of the rails on the board. You can plug in wires to the other slots in those rails to connect other things to the respective pin on the pico. Some of the pins have specific functions, for instance, if you plugged in a wire to the slot with the blue dot on top it would connect to the ground pin on the pico. Other pins are considered "general purpose", meaning that they have no built-in use but are meant to connect other compenents into as needed for any given project. You can find a [complete listing of the pins and their usages here.](http://www.espruino.com/Pico)

The pinout graphic may seem a bit overwhelming, but the imporant bits to know for now are pretty easy: All of the pink and blue circuit traces match up with the orientation of the physical board, make sure you are orientating the board (physically at first and then later you can rotate in your mind) when you are comparing it to the diagram.

The most important info is closest to the circuit traces. The thin black outlined boxes with white background that say things like "B5", "A7", "GND", "3.3" etc. The "3.3" stands for volts and it is the main power pin. Some circuits may use it, but others may not. "GND" stands for ground; all circuits will use it. The ones with "BAT" in the name are only for use with batteries. All other pins have a name comprised of a letter and number. You use this name to refer to the pin in your code to read or write its value (turn it on or off, or if it is PWM set it's output level). So if you connected an LED between pin B5 and GND and then used code like `digitalWrite(B5, 1);` the LED should turn on. Then execute `digitalWrite(B5, 0);` it should turn back off. _(note: The long leg of the LED is positive, the short leg is negative. So power should come in from the long and flow out to GND through the short.)_

!['LED Circuit'](basic_led_circuit.PNG?raw=true)

A good first project is to plug in a red, yellow, and green LED to 3 different GPIO pins and write a program to make them behave like traffic lights. You can use the setTimeout() method to delay changing to the next color light. 

Once you get that down you can branch out and explore other types of electrical components or more complex projects. You can find many [ideas and examples here](http://www.espruino.com/Tutorials). There are several LEDs in the bag of parts including some multicolor ones. There is also a few buttons and a speaker, and a photoresistor(light sensor). You can try experimenting with them. 