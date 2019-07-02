# imu_calibration of Sparkfun Razor IMU M0 Record
IMU ros wiki: https://www.evernote.com/l/ATsbvRpS7nZLiKoklp756MNPt2dNEVbX-9I  
IMU sparkfun tutorial: https://www.evernote.com/l/ATu8VJMjdIVCuI5qk5EX4V7FMfbtIgb-cU8  
IMU definition: https://www.evernote.com/l/ATvsxBwsDKNBBYuEWXNob-FRUMQBjc3EM0o  
IMU calibration: https://www.evernote.com/l/ATuYjFLlitlAXqQWwsF9eZbvZbbYLUekXN0  

Arduino library: ```Arduino/razor_imu_9dof/src/Razor_AHRS```  
Using for firmware update and seeing acc/mag/gyro output  

Processing library: ```sketchbook/libraries/EJML/library```  
Would be import by magnetometer_calibration/Processing/Magnetometer_calibration/Magnetometer_calibration.pde  

## roughly procedure
usage
1. Setup the Arduino IDE environment, enable to upload firmware to IMU
2. open Arduino > file > sketchbook > razor_imu_9dof > src > Razor_AHRS
3. Run, then open serial, get the RPY result that ROS could use
calibration
1. Open Arduino serial console, now is RPY mode for ros
2. enter ```#oc```, now is acc mode for calibration. Start to calibrate imu using gravity. enter ```#oc```to reset.
3. enter ```#on```, now is mag mode for calibration. This is old method skip.
4. enter ```#on```, now is gyro mode for calibration. Put imu on the table 10s. enter ```#oc```to reset.
5. Setup the Processing IDE environment, enable to run Magnetometer_calibration.pde
6. Open Processing, run Magnetometer_calibration.pde, now is mag calibration.
7. update all parameters in .yaml and arduino(re-update firmware)

## Result
<img src="https://github.com/shannon112/imu_calibration/blob/master/result/matlab_plot_v2.png" width="840">

<img src="https://github.com/shannon112/imu_calibration/blob/master/result/processing_plot_v2.png" width="270"> <img src="https://github.com/shannon112/imu_calibration/blob/master/result/ros_gui.png" width="560">
