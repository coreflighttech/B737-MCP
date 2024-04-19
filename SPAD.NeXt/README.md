
Special thanks to @1L2P (Discord ID: 1L2P#5598) for his excellent work!

Firmware tested with SPAD_v0.9.12.92 Full Release

MCP communicates with SPAD.neXt via SerialV2.
Baud Rate is 115200

How to install firmware -> https://github.com/coreflighttech/B737-MCP/tree/main/Uploader

Available SPAD complete device Snippet #10858

R10: Internal device features:
- Send (-1) to clear CRS, HDG or IAS displays
- Send (-9999) to clear VS or ALT displays
- Send (-111) to display dashes on IAS or HDG displays (---)
- Send (-11111) to display dashes on VS display (-----)
- Send (-99) to display 'Std' on left or right CRS displays
- Turn on/off backlight by pressing C/O + CMDA and C/O + CWSA (MCP needs to be externaly powered)
- Set Backlight brightness level by pressing C/O and turning V/S encoder
- Turn on/off all display digits by pressing C/O + CMDB and C/O + CWSB
- Set Display brightness level by pressing C/O and turning RIGHT COURSE encoder
- Soft reset by pressing N1 and SPEED

To manage MCP digits and backlight brightness from SPAD, search for these variables.
- DISPLAY_BRI : MCP digits brightness from 0 to 15 (DEVICE:1L2P/CFT737MCP/DISPLAY_BRI)
- BACKLIGHT_BRI : MCP backlight brightness from 0 to 255 (DEVICE:1L2P/CFT737MCP/BACKLIGHT_BRI)

*** Old Firmware ****

R09: Internal device features:
- Send (-1) to clear CRS, HDG or IAS displays
- Send (-9999) to clear VS or ALT displays
- Send (-111) to display dashes on IAS or HDG displays
- Send (-11111) to display dashes on VS display
- Turn on/off backlight by pressing C/O + CMDA and C/O + CWSA (MCP needs to be externaly powered)
- Set Backlight brightness level by pressing C/O and turning V/S encoder
- Turn on/off all display digits by pressing C/O + CMDB and C/O + CWSB
- Set Display brightness level by pressing C/O and turning RIGHT COURSE encoder
- Soft reset by pressing N1 and SPEED

R07: Internal device features:
- Turn on/off backlight by pressing C/O + CMDA and C/O + CWSA (MCP needs to be externaly powered)
- Set Backlight brightness level by pressing C/O and turning V/S encoder
- Turn on/off all display digits by pressing C/O + CMDB and C/O + CWSB
- Set Display brightness level by pressing C/O and turning RIGHT COURSE encoder
- Soft reset by pressing N1 and SPEED

R06: Internal device features:
- Turn on/off backlight by pressing C/O + CMDA and C/O + CWSA (MCP needs to be externaly powered)
- Set Backlight brightness level by pressing C/O and turning V/S encoder
- Turn on/off all display digits by pressing C/O + CMDB and C/O + CWSB
- Set Display brightness level by pressing C/O and turning RIGHT COURSE encoder
- The version is displayed on the led segments digits
- Pre-config is available as Snippet #6477 or "Flight Core Technologies PMDG 737 MCP"

![Screenshot](https://user-images.githubusercontent.com/53659578/193845938-f0ef2aed-1326-4257-a87d-9a4b7bee52e3.png)

*** History ***
 -> r01 Initial release 
 
 -> r02 Overflow issue fix when altitude to display is over 32768 feet (15 bits were not enougth ;-)) 
 
 -> r03 clean overflow with int32 and not double, add negative values for displays, fix decimal point missing in IAS/MACH display, slow down checks other than encoders, SPAD 0.9.12.95 Serial V2 update,
 
 -> r04 VIP PID SPAD registration, State scan enabled, new VIRTUAL_POWER variable exposed 
 
 -> r05 SPAD serial init workarounds, add soft reset by pressing N1 and SPEED
 
 -> r06 SPAD GUI Led state enhancement
 
 -> r07 SPAD 0.9.13.7 udpate, backlight and leds/digits auto turn OFF on 300s SPAD no ping timeout, remove negative display feature on CRS, IAS & HDG (was confusing, send any <0 value to clear digits)
 
 -> r08 The "Darewell" Incident: 0.67 MACH display mystery fix 
 
 -> r09 A320 DASH display option sending -11111 (V/S) or -111 (HDG, IAS)
 
 -> r10 Send -99 to diplay 'Std' on CRS left or right displays 


