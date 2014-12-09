## Instrumentation List
| Sensor                        | Metric                            | Unit                      | Nominal Range | Nominal Tolerance  |
| -------                       | -------------------               | ----                      | -----------   | ------------------ |
| [WiFi][WiFi]                  | AP Scan                           | -                         | - 			      | -		 	             |
| [SD][SD]                      | Logging                           | -                         | -             | -		 	             |
| [LDR][LDR]                    | Light/Luminosity                  | Lux (lx)                  | -             | -		 	             |
| [HTU21D*][HTU21D]             | Humidity <br> Ambient Temperature | RH (%) <br> &deg;C        | -             | -		 	             |
| [TMP006*][TMP006]             | IR Temperature                    | &deg;C                    | - 		        | -		 	             |
| [TMP007*][TMP007]             | IR Temperature                    | &deg;C                    | - 		        | -		 	             |
| [BMP180*][BMP180]             | Pressure <br> Altitude            | Pa <br>m                  | - 		        | -		 	             |
| [Electret Mic][MIC]           | Sound                             | dB?                       | - 		        | -		 	             |
| [Sharp Particle Counter][SPC] | Air Quality/Dust Density          | mg/m<sup>3</sup>          | - 		        | -		 	             |
| [INA219][Current]             | Current Draw <br> Battery Voltage | mA <br> V                 | - 		        | -		 	             |
| [Piezo Strip][Piezo]          | Vibration/Motion                  | -                         | - 		        | -		 	             |
| [Vibration Sensor][Vib]       | Vibration/Motion                  | -                         | - 		        | -		 	             |
| [MMA8451][Accel]              | Velocity <br> Acceleration        | m/s <br> m/s<sup>2</sup>  | - 		        | -		 	             |
| [GPS][GPS]                    | Location                          |                           | - 		        | -		 	             |

 \* Sensor capable of returning on-board/ambient temperature reading

## Header String Format
```
Node ID,Time Stamp (ms),VarName1,VarName2,VarName3, ... ,VarNameN,
```
Example header line:
```
Node ID,Time Stamp (ms),Light (lx),Humidity (%),Pressure (Pa),Altitude (m),Current (mA),Voltage (V),
```
## Output String Format
```
nodeID,timeStamp,Val1,Val2,Val3, ... ,ValN,MAC1,RSS1,MAC2,RSSI2, ... , MACN,RSSIN,
```
Example header line with output string:
```
Node ID,Time Stamp (ms),Light (lx),Humidity (%),Pressure (Pa),Altitude (m),Current (mA),Voltage (V),
1      ,2451           ,434       ,63          ,101325       ,923         ,124         ,3.856      ,01:02:03:04:05:06,50,07:08:09:0a:0b:0c,70,
```

## Code Reference
| Sensor                        | Metric                            | I<sup>2</sup>C Address  | Header Strings (Var Names)                      |
| -------                       | -------------------               | ----------------------  | --------------------------                      |
| [WiFi][WiFi]                  | AP Scan                           | -                       | -                                               |
| [SD][SD]                      | Logging                           | -                       | -                                               |
| [LDR][LDR]                    | Light/Luminosity                  | -                       | `Light (lx) `                                   |
| [HTU21D*][HTU21D]             | Humidity <br> Ambient Temperature | 0x40                    | ` Humidity (%),`<br>`Ambient Temperature (°C),` |
| [TMP006*][TMP006]             | IR Temperature                    | 0x44                    | `IR Temperature (°C), `                 		    |
| [TMP007*][TMP007]             | IR Temperature                    | 0x44                    | `IR Temperature (°C),`                  		    |
| [BMP180*][BMP180]             | Pressure <br> Altitude            | 0x77                    | `Pressure (Pa),`<br>`Altitude (m),`             |
| [Electret Mic][MIC]           | Sound                             | -                       | `Noise (dB),`                                	  |
| [Sharp Particle Counter][SPC] | Air Quality/Dust Density          | -                       | `Air Quality (mg/m^3), `                        |
| [INA219][Current]             | Current Draw <br> Battery Voltage | 0x41                    | `Current (mA),`<br>`Voltage (V), `              |
| [Piezo Strip][Piezo]          | Vibration/Motion                  | -                       | `Motion, `                                  	  |
| [Vibration Sensor][Vib]       | Vibration/Motion                  | -                       | `Motion`,                                   	  |
| [MMA8451][Accel]              | Velocity <br> Acceleration        | 0x1C                    | -                                               |
| [GPS][GPS]                    | Location                          |                         | -                                               |

### Outputs
- RGB LED
- Piezo Buzzer

## Notes
- Using Spark Dev to work offline..
- Battery charging (Solar panel integration in the future)

## Libraries
All libraries have been ported and moved to a local folder. The following links are for reference:

- HTU21D: https://github.com/romainmp/HTU21D
- TMP006: https://github.com/krvarma/Sparkfun_TMP006_SparkCore
- TMP007: https://github.com/adafruit/Adafruit_TMP007_Library
- BMP180: https://github.com/krvarma/Adafruit_BMP085_Library
- SD Card: https://github.com/technobly/SparkCore-SD
- WiFi Scanning: https://gist.github.com/dmiddlecamp/11294083
- INA219: https://github.com/adafruit/Adafruit_INA219
- MMA8451: https://github.com/adafruit/Adafruit_MMA8451_Library
- Unified Sensor Lib: https://github.com/adafruit/Adafruit_Sensor

## Guides/WiKis
- HTU21D: https://learn.sparkfun.com/tutorials/htu21d-humidity-sensor-hookup-guide
- TMP006: https://learn.sparkfun.com/tutorials/tmp006-hookup-guide
- TMP007: https://learn.adafruit.com/adafruit-tmp007-sensor-breakout?view=all
- BMP180: https://learn.sparkfun.com/tutorials/bmp180-barometric-pressure-sensor-hookup-
- Sharp Particle Sensor: http://www.dfrobot.com/wiki/index.php/Sharp_GP2Y1010AU, http://www.howmuchsnow.com/arduino/airquality/
- INA219: https://learn.adafruit.com/adafruit-ina219-current-sensor-breakout?view=all
- MMA8451: https://learn.adafruit.com/adafruit-mma8451-accelerometer-breakout?view=all
- GPS:

[WiFi]: https://www.spark.io/
[SD]: http://www.adafruit.com/products/254
[HTU21D]: https://www.sparkfun.com/products/12064
[BMP180]: https://www.sparkfun.com/products/11824
[TMP006]: https://www.sparkfun.com/products/11859
[TMP007]: http://www.adafruit.com/product/2023
[MIC]: https://www.sparkfun.com/products/9964
[Piezo]: https://www.sparkfun.com/products/9198
[Vib]: http://www.adafruit.com/products/1766
[SPC]: https://www.sparkfun.com/products/9689
[LDR]: http://www.adafruit.com/products/161
[Current]: http://www.adafruit.com/products/904
[Accel]: http://www.adafruit.com/product/2019
[Current]: http://www.adafruit.com/products/904
[GPS]: http://www.adafruit.com/product/746
