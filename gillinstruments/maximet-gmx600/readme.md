## MaxiMet GMX600 Total Weather Station

The GMX600 is one of the Gill Instruments line of 
[compact weather stations](http://gillinstruments.com/products/anemometer/maximet-compact-weather-stations.html).
The entire GMX-series has similar functionality and these examples should be
straightforward to adapt to sibling models. 


### SDI-12

Refer to the user manual for placing the device in SDI-12 mode. 

#### Wiring

| Pin # | Signal                 | CR6 terminal |
|:-----:|------------------------|:------------:|
|   9   | SDI-12 data signal     |      U1      |
|   1   | SDI-12 signal ground   |    &#x23da;  |
|   -   | cable shield           |    &#x23da;  |
|   2   | 12V power input        |      12V     |
|   3   | power ground           |      G       |

#### Comparison

**Advantages:**

* Rapid integration (simple, standardized data protocol)
* Long cable lengths (up to 90m, only 3 wires total)

**Disadvantages:**

* Slow (too slow to query all parameters at 1Hz)
* Limited data set (Wind Sensor Status code not available, only GPS position/altitude
    available)

#### Messages

| Parameter                   |  M! | M1! | M2! | M3! | M4! | M5! |
|-----------------------------|-----|-----|-----|-----|-----|-----|
| relative wind direction     |  X  |     |  X  |     |     |     |
| relative wind speed         |  X  |     |  X  |     |     |     |
| corrected wind direction    |  X  |     |     |     |     |     |
| corrected wind speed        |  X  |     |     |     |     |     |
| temperature                 |     |  X  |     |     |     |     |
| relative humidity           |     |  X  |     |     |     |     |
| dew point                   |     |  X  |     |     |     |     |
| barometric pressure         |     |  X  |     |     |     |     |
| status code                 |  X  |  X  |  X  |     |     |     |
| precipitation intensity     |     |     |     |  X  |     |     |
| precipitation total         |     |     |     |  X  |     |     |
| solar radiation             |     |     |     |     |  X  |     |
| sunshine hours              |     |     |     |     |  X  |     |
| signed latitude (integer)   |     |     |     |     |     |  X  |
| signed latitude (fraction)  |     |     |     |     |     |  X  |
| signed longitude (integer)  |     |     |     |     |     |  X  |
| signed longitude (fraction) |     |     |     |     |     |  X  |
| height above MSL            |     |     |     |     |     |  X  |
| **For GMX600+Precip+GPS**   |**X**|**X**|     |**X**|     |**X**|

> Note: `M6!` command only contains date/time and status code

