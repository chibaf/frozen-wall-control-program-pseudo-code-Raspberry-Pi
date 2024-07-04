# frozen-wall-control-program-pseudo-code-Raspberry-Pi

frozen-wall-control-program-pseudo-code-Raspberry-Pi

## pseudo code of control

<pre>
  time t11,t12,t13,t15,t16;  // interval times given
  // T11=t11_on+t11_off
  // T12=t12_on+t12_off
  // T13=t13_on+t13_off
  // T15=t15_on+t15_off
  // T16=t16_on+t16_off
  while true:
    TLog=read_logger()  // read logger
    ADC=read_adc()  // read adc
    Current=read_current()   // read yageta current
    writeLog(TLog,ADC,Current)   // write log file
    // id=id11 // SSR_11
    if t11 &ge; T11:
      t11on=func11(TLog,ADC)  // calc on/off time t1,t2
      t11=0
    else
      if t11 &le; t11on
        GPIO(11,on)   // make GPIO 11 on
      elseif t11on &lt; t11 &le; T11
        GPIO(11,off)  // make GPIO 11 off
      increse t11
    // id=id12 // SSR_12
    if t12 &ge T12:
      t12on=func12(TLog,ADC)  // calc on/off time t1,t2
      t12=0
    else
      if t12<=t12on
        GPIO(12,on)
      elseif t12on<t12<=T12
        GPIO(12,off)
      increse t12
    // id=id13 // SSR_13
    if t13 &ge; T13:
      t13on=func13(TLog,ADC)  // calc on/off time t1,t2
      t13=0
    else
      if t13 &le; t13on
        GPIO(13,on)
      elseif t13on &lt; t13 &le; T13
        GPIO(13,off)
      increse t13
    // id=id15 // SSR_15
    if t15 &ge; T15:
      t15on=func15(TLog,ADC)  // calc time of on
      t15=0
    else
      if t15<=t15on
        GPIO(11,on)
      elseif t15on &lt; t15 &le; T15
        GPIO(15,off)
      increse t11
    // id=id16 // SSR_16
    if t16 &ge; T16:
      t16on=func16(TLog,ADC)  // calc on/off time t1,t2
      t16=0
    else
      if t16 & le; t16on
        GPIO(16,on)
      elseif t16on &le; t16 &le; T16
        GPIO(16,off)
      increse t16

</pre>

## GPIO pin no of Raspberry pi

![GPIO 27](https://github.com/chibaf/rozen-wall-control-program-pseudo-code-Raspberry-Pi/assets/1296728/80a3d6c9-122e-4ed4-9d26-1e6abda28791)

￼11,12,13=heater   16=propeler    15=pump
