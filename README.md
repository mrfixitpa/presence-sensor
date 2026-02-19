# presence-sensor

## setup
*see https://esphome.io/components/captive_portal/ for more details about wifi setup*

- plug in usb c
- wait about a minute
- open wifi networks on phone/PC and look for "presence-sensor fallback hotspot", and connect to this
<img width="1080" height="573" alt="wifi" src="https://github.com/user-attachments/assets/eab997db-2ac0-4975-b597-40db74dea888" />

- once connected go to http://192.168.4.1/ on your browser, on the device you just connected to the sensor
- from there you can pick what wifi network for the device to use, and enter a password
- in home assistant goto "settings->devices and services", the presense sensor should show up as a discovered device
  - you'll need to enter an encryption key to add the device, this is:
    - utmYBjWAI1uV7/qyZuBOGzbUmBdFV3ICbfte01tIOOU=

## debug - can't connect to wifi
- you should be able to connect via the fallback hotspot, but if that really isn't working, then you can manually install a firmware image with the wifi hard coded
- install esp-home add-on (ESPHome Device Builder)
- create a new device
- copy over YAML from https://github.com/RyanChomistek/presence-sensor/blob/main/presence-sensor.yaml
- install that manually onto the device (this will probably prompt you to add secrets for your wifi)

## debug - logging
- if you cannot see it in home assistant, or having wifi issues
- connect sensor to PC using esb
- goto https://web.esphome.io/?dashboard_wizard
- connect to the sensor
- click the button for logging (you'll probably then need to hit the button to reset to get usefull logs from boot)
