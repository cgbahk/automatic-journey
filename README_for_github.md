* LICENSE notice
    * Let me know if therer is any violation of license, or citation required.
    
* Caution on implementation
    * In case using multiple MPUs at once, one should concern about power requirement. Voltage should may not be generated from Arduino, but from auxilary stable power source
    * For multiple MPUs implementation, __Voltage quality matters!!__
        * Explicit VDDIO may increase stability (SJ1, or jumper1 on SparkFun board should be disconnected) - this may not effective as expected though...
        * External (not Arduino generating) and more stable VDD(3V3) with sufficiently large power for MPUs may increase stability as well.

* Caution on jumper
    * `SparkFun Board` has two jumpers
        * SJ1: By default, SJ1 is connected and VDD == VDDIO. This configuration seems reasonably stable for fast prototyping, but may lack power reduction in multiple MPU implementation. Disconnect to use VDDIO explicitly and consider to add decoupling capacitor recommended by datasheet of `MPU-9250`.
        * SJ2: By default, AD0/SDO pin of MPU-9250 is connected to GND, and __AD0/SDO PTH (hole) of `SparkFun Board` is disconnected__. To use SPI communication, this jumper connection should be altered.

* Feature
    * Self-test (plan)
