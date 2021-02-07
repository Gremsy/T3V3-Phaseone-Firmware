# T3V3-Phaseone-Firmware
Firmware used to interface with Phaseone Camera via COM4. 

# What's new?

## Sending IMU angle
- Serial communication at 115200bps via COM4 of gimbal with level shifter
- Message format based on NEMA PASHR sentence
- Up to 50 messages/sec

- PhaseOne will retrieve the Heading, Roll and Pitch only, so custom message can be based on the following,
    " $GREMSYIMU,HHH.HH,T,RRR.RR,PPP.PP,ST*CS "
    + HHH.HH - Heading value in decimal degrees
    + T - displayed if heading is relative to true north or to heading of drone.
    + RRR.RR - Roll in decimal degrees.
    + PPP.PP - Pitch in decimal degrees.
    + ST – status of IMU information (valid/not valid…)
    + CS – checksum


## Control gimbal in the follow mode
- Gimbal allows control in follow mode by using remote  control or gSDK

## Control gimbal with LightBridge 2 with DJI's Remote Control.
- In Single mode
  + C1 button switch mode (LOCK -> FOLLOW -> MAPPING)
  + C2 button switch control between TILT and PAN axis.
  + C2 button press hold > 2 seconds. Turn off Gimbal.
- In Dual Mode
  + C1 button switch mode (LOCK  FOLLOW  MAPPING)
  + C2 button press hold > 2 seconds. Turn off Gimbal.
- Refer to: https://www.youtube.com/watch?v=p9fpLAZofRc&t=7s

## Control gimbal with Herelink with Pixhawk Flight Controller.
Use S.Bus signal output from the Herelink for simultaneous control of Autopilot, Gimbal and camera as well.
- In Single mode
  + Scroll wheel controls the TILT or PAN axis (Channel 10)
  + Top button (Right) controls the Gimbal mode including 3 states (Toggle PAN or TILT and Reset Position) (Channel 9)
  + C button controls zoom in for camera (Channel 14)
  + D button controls zoom out for camera (Channel 14)
  + Trigger Camera (Channel 7)

## Go to home position when switching the gimbal mode automatically.

## Control gimbal with gSDK.
- Gremsy SDK to meet the requirements of those building solutions for
various industrial applications.
- Adjust the speed, smooth and direction control of each axis. 
- Adjust Data Transmission Rates of each message.

## Control gimbal with Pixhawk.
- Automated aiming of the camera at a Region of Interset or manual control
through MAVLink message.

## Detect errors when initialization.
- Gimbal will dectect automatically when initialization and pop-up error on the
new gTune with troubleshooting guide.

## Start-up at random position.
