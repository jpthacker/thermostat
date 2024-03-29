# A Thermostat

A simple program to manage a thermostat. Here is the
specification for the initial MVP of the program:

* The Thermostat starts with an initial temperature of 20 degrees
* You can increase the temperature with an `up` method
* You can decrease the temperature with a `down` method
* The *minimum possible temperature* is 10 degrees
* The *Power saving mode* is *on by default* but it can also be turned off
* *If power saving mode is on*, the maximum temperature is 25 degrees
* *If power saving mode is off*, the maximum temperature is 32 degrees
* You can reset the temperature to 20 with a `reset` method
* You can ask about the thermostat's *current energy usage*: < 18 is low-usage, <= 25 is
  medium-usage, anything else is high-usage.

```javascript
const thermostat = new Thermostat();

thermostat.getTemperature(); // should return 20

thermostat.up(2);
thermostat.getTemperature(); // should now return 22

thermostat.down(1);
thermostat.getTemperature(); // should now return 21

thermostat.setPowerSavingMode(true); // PSM is now on, max temperature is 25

thermostat.up(10);

thermostat.getTemperature(); // should be 25 (max reached)

thermostat.setPowerSavingMode(false); // PSM is now off, max temperature is no more 25

thermostat.up(1);
thermostat.getTemperature(); // should now return 26

thermostat.reset();
thermostat.getTemperature(); // should be back to 20
```
