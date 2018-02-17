# daliMaster

This is an Arduino™ library to control your DALI lamps with the brand new [daliMaster](www.ebay.d) shield, with buit-in DALI bus power supply system. b:boom::boom:m!

## Description

### What is DALI?

DALI (Digital Addressable Lighting Interface) is a powerful protocol to control lighting. Through DALI you can dimmer your led lamps, ask them status, recall a predefined scenario and so on. Of course, the ballast that powers your lamp must be DALI compatible and acts as a DALI slave. You want more information about DALI, don't you? I thinks this is not the right place for that but I'm gonna leave you some useful links to the bottom of this page.

### Can I use DALI with my Arduino™?

Well, the answer is YES.

### How?

With [daliMaster](http://www.ebay.com)! As the name suggests, that shield transforms your Arduino™ in a DALI master, acting as a bridge between I2C interface and DALI bus. This shield is powered by [LW14](http://shop.codemercs.com/media/files_public/okutobbwyxn/LW14_Datasheet.pdf) chip by [Code Mercenaries](https://www.codemercs.com/en/). Let's make an example to explain how it works.

## Getting Started

* Fit [daliMaster](www.ebay.d) on your Arduino™

* Make connections (you can find an example [here](schema.jpeg))
  * Connect your lamps to their ballasts
  * Connect your ballast to mains..be careful!
  * Connect your ballasts and [daliMaster](http://www.ebay.com) to DALI bus
  * Connect your 24V DC power supply to mains and to [daliMaster](http://www.ebay.com)..again, be careful!

* If I'm right, now you should have all of lamps on. Let's turn them off.

* Connect Arduino™ to your computer.

* Download this library and load **daliMaster/examples/serialControl.ino**

* Now open serial monitor, select 115000 as baudrate and you should see:
```
daliMaster start..
i2c master begin..
device(0x23) is ready!
```
* Well, write and send this command:
```
-d -b 0
```
* If everything went well your lamps now are off. But we don't like darkness, so let's switch them on to the minimum:
```
-d -b 1
```
* Cool! Let's push them to maximum:
```
-d -b 254
```
Easy, isn't it? Now you can modulate all lamps from 0 up to 254 with those simple commands. :thumbsup:

## Next

See more informations about serial commands [here](examples/serialControl/README.MD). See also the following links to know more about DALI and LW14 commands.

## Useful links

### LW14
* [LW14 datasheet](http://shop.codemercs.com/media/files_public/okutobbwyxn/LW14_Datasheet.pdf)

### DALI
* [main commands](http://www.tanzolab.it/www/CM3-HOME_test/dali_commands.pdf)
* DALI international standard (English/French) [60929 © IEC:2006](http://jnhb.fszjzx.com/upload/biaozhun/pdf/IEC60929Y2006.PDF)

## Built With

* [Eclipse IDE for C/C++ Developers](https://www.eclipse.org/downloads/packages/eclipse-ide-cc-developers/lunar)
* [Arduino IDE](https://www.arduino.cc/en/main/software)

## Versioning

* v.1 First release 21/01/2018

## Credits

* **Code Mercenaries** - *Original Raspberry Pi library for LW14 Modules* - [LED-Warrior14](https://www.codemercs.com/en/33-led-warrior/270-led-warrior14-2)

see [credits.md](credits.md) file for details.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
