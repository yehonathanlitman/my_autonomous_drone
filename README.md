# Setting up Pixhawk to do VIO:
mavlink stream -d ${MAVLINK\_COMPANION\_DEVICE} -s HIGHRES_IMU -r 200 in /etc/init.d/rcS (plug sd card to computer)
edit px4/Firmware/src/modules/mavlink\_main\.cpp (ATTITUDE_QUATERNION parameter = 200)
then edit camera\_trigger\_params.c in px4/Firmware/src/drivers/camera_trigger

  1.GPIO trigger mode

  2.TRIG_INTERVAL: 50.0 ms (20 FPS)

  3.TRIG_POLARITY: 0 (active low)

  4.TRIG\_ACT\_TIME: 0.5 ms 

  5.TRIG_MODE: 1

  6.TRIG_PINS: 56

enable triggering through mavcmd in launch file
modify point grey driver
finally modify covariance and noise parameters in rovio info file
