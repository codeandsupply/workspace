# C&S Workspace WiFi & Internet Outage Troubleshooting Guide

> _“Don’t just randomly power cycle stuff, yinz.”_

Before doing anything inside the network closet, check these things:

1. Try toggling WiFi on the device that cannot access the Internet.
1. Are the Code & Supply WiFi SSIDs detected on the device?
    * Yes: WiFi is up! Connection beyond the AP is suspect.
    * No: AP(s) is/are down. Is the building power on?
1. Are other devices able to access the Internet through the Code & Supply WiFi SSIDs?
    * Yes: It’s just the problem device. Try rebooting it or messing with its IP settings.
    * No: Connection beyond the AP is suspect.
1. Can you access intranet resources? 
    * Gateway: https://10.10.220.1
    * Unifi Controlller: https://10.10.220.22
    * Yes: Internet is down! ISP or gateway is suspect.
    * No: Intranet is down! Switch or gateway is suspect.

Internet outage troubleshooting quick steps, after each check the above:

1. Powercycle Comcast modem/router (tall black box) by unplugging its power cord from the unit. Reboot will take 1-2 minutes. Do not powercycle the power strip!
1. Powercycle the Ubiquiti USG (short white box) by unplugging its power cord from the unit. Reboot will take 3-5 minutes. Do not powercycle the power strip!
1. Restart WiFi access points
    1. Access the local Unifi controller at https://10.10.220.22 using the appropriate credentials.
    1. Go to https://10.10.220.22:8443/manage/site/default/devices/1/50
    1. Restart the WiFi access points by clicking Restart. Do not Upgrade the access points, though.
