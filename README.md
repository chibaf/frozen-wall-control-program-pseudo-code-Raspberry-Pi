# frozen-wall-control-program-pseudo-code-Raspberry-Pi

frozen-wall-control-program-pseudo-code-Raspberry-Pi

<pre>
  time t11,t12,t13,t15,t16;  // interval times given
  // t11=t11_on+t11_off
  // t13=t12_on+t12_off
  // t15=t13_on+t13_off
  // t11=t15_on+t15_off
  // t11=t16_on+t16_off
  while true:
    TLog=read_logger()  // read logger
    ADC=read_adc()  // read adc
    Current=read_current()   // read yageta current
    writeLog(TLog,ADC,Current)   // write log file
    // id=id11 // SSR_11
    if T11 > t11:
      (t1,t2)=func11(TLog,ADC)  // calc on/off time t1,t2
      T11=0
      ssr11(t1,t2)  // ssr on/off
    else
      increse T11
    // id=id12 // SSR_12
    if T12 > t12:
      (t1,t2)=func12(TLog,ADC)  // calc on/off time t1,t2
      T12=0
      ssr12(t1,t2)  // ssr on/off
    else
      increase T12
    // id=id13 // SSR_13
    if T13 > t13:
      (t1,t2)=func13(TLog,ADC)  // calc on/off time t1,t2
      T13=0
      ssr13(t1,t2)  // ssr on/off
    else
      increase T13
    // id=id15 // SSR_15
    if T15 > t15:
      (t1,t2)=func15(TLog,ADC)  // calc on/off time t1,t2
      T15=0
      ssr15(t1,t2)  // ssr on/off
    else
      increase T15
    // id=id16 // SSR_16
    if T16 > t16:
      (t1,t2)=func16(TLog,ADC)  // calc on/off time t1,t2
      T16=0
      ssr16(t1,t2)  // ssr on/off
    else
      increase T16

</pre>

![GPIO 27](https://github.com/chibaf/rozen-wall-control-program-pseudo-code-Raspberry-Pi/assets/1296728/80a3d6c9-122e-4ed4-9d26-1e6abda28791)

￼11,12,13=heater   16=propeler    15=pump
