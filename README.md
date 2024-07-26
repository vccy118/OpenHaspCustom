# OpenHaspCustom
Custom openHasp with cctv and alarm panel solutions for HomeAssistant integration

ESP Boards:
ESP32-S3 N16R8 Black Board variant pinout (Chip:ESP32-S3-Wroom-1; Board:YD-ESP32-23 2022-V1.3)
1. TFT_MISO=17
2. TFT_MOSI=8
3. TFT_SCLK=18
4. TFT_DC=5
5. TFT_CS=16 
6. TFT_RST=-1        ; Connect to RST pin on ESP32s3
7. TFT_BCKL=13       ; None, configurable via web UI (e.g. 21)
8. TOUCH_CS=3        ; (can also be 14 or )

ESP-Wroom-32 38 Pin (cctv images doesn't work due to lack of PSRAM)
1. TFT_MISO=19
2. TFT_MOSI=23
3. TFT_SCLK=18
4. TFT_DC=2
5. TFT_CS=15
6. TFT_RST=4         ; RST
7. TFT_BCKL=21       ; None, configurable via web UI (e.g. 21)
8. TOUCH_CS=5        ; (can also be 14 or )

LCD touch panel:
2.8 Inch SPI TFT LCD Touch Panel ILI9341 (Touch Controller:XPT2046)
Special fix needed for this panel:
At the default SPI_TOUCH_FREQUENCY=2500000, the Y axis will be stuck at 4095 and the Z axis (touch pressure) will fluctuate around 1000, which will cause the touch to be unusable.
With a lower SPI_TOUCH_FREQUENCY=1000000, the Y axis is still stuck at 4095, however the Z axis will fluctuate around 300.
The default openHasp actuation pressure threshold is 500, thus allowing the touch panel to accept new inputs as long as the Z pressure is above 500.

Photos of esp boards and LCD touch panel included for reference.

Files to be modified in Gitpod (https://openhasp.com/0.7.0/firmware/compiling/gitpod/) and working bin files in respective board folders.

List of other files in "CCTV and Alarm Panel" folder:
1. openHasp pages.jsonl
2. Home Assistant integration yaml file
3. Custom template sensor yaml file
4. Home Assistant automations
5. Sample Screenshots for reference
