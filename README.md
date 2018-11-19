# 8-pin-pic-breakout
Breakout board for 8-pin Microchip PIC devices (10/12/16 family), for SMD and DIP.

![Render](https://i.imgur.com/06RZ8fx.jpg)

## What is this?
This is a flexible breakout board for the 8-pin variants of PIC family devices. Most (all?) 8-pin PICs share the same pinout so it should be compatible with all of them. It has been designed with a PIC18F18313 in mind, but it should work perfectly with the classic PIC12F675. It's compatible with DIP and SOIC packages. Why would you need a breakout board for a DIP, you ask? Read on and you will find out!

## What's special about this breakout?
I designed this breakout to be as flexible as possible. It includes a few onboard components:
- **5-pin header for ICSP:** It's a programming header. The pinout is compatible with PICKit2, 3 and 4. You can solder an angled .1" pin header here.
- **0603-size decoupling capacitor:** You can (and should) solder a .1uF (100nF) capacitor in every VDD pin of every IC in your board. It's not only good practice, but most manufacturers specify it in the datasheet.
- **0805-size MCLR resistor at MCLR:** PICs have an active-low RESET input. This board lets you solder a 0805 resistor to keep MCLR tied to VDD. This may be optional. Older PICs require it. Some PICs allow to disable VDD altogether, and newer PICs have an internal resistor. So you need to check your datasheet.
- **0805-size resistors for PGC and PGD:** These resistors are in series with the PGC/ICSPCLK and PGD/ICSPDAT pins. They are not strictly necessary (you can short them) but sometimes it's good for extra protection. A compromise value is 47-100 ohms. But you can use a higher value for added piece of mind.
- **Extra row of VDD and GND:** You can connect other breakout boards here. It's always nice to have extra power pins to power other breakouts.

## How to use it
Well, there are several ways to use this board. 

### Standard breakout 
In this mode, the board is just a breakout board. You solder a 8pin SOIC PIC and that's it. You can then solder wires into the provided wire pads. You can also use a DIP PIC (weird flex but ok).

### Standard breakout with programming header
Based on the "Standard breakout" mode, solder a 5-pin angled connector. Now it makes a little more sense with a DIP package. Remember to solder R2 and R3!

### DIP programmer
Instead of soldering a PIC directly, solder a 8-pin socket and an angled connector. You can now easily program 8 pin DIPs with your PICKIT2-3-4. Remeber to solder in R2/R3 or bridge them.

### SOIC to DIP adapter
Solder a SOIC IC, and solder two 4-pin, .1" short-pin headers sticking out through the bottom, to the innermost pin headers. It can now act as an adapter for your breadboard. You can solder a programming header too. 

### Breadboard adapter
While SOIC to DIP works great, for breadboards it may make more sense to solder to the outermost headers, for added stability when using it in a breadboard.

### Full-blown development board
You can solder in a PIC and all headers. The headers can be male or female, or female with long pins (male on the bottom, good for sticking into breadboards, and female on the top for extra female pins). The same goes for the extra power connectors. Or you can use long-pin male headers. Or just short male headers. Or just female headers. You can customize it to whatever you need.
