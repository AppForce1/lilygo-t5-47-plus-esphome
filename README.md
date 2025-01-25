Based on:

https://github.com/paviro/ESPHome-ePaper-Calendar/blob/main/home-assistant/configuration.yaml

## Integrating with Home Assistant

To make your ePaper calendar work properly, you need to add some sensors to Home Assistant by following these additional steps:

### 1. Configuration Sensors and Integrations:
   - Append the contents of `configuration.yaml` from this project to your Home Assistant `configuration.yaml` file without overwriting existing configurations you have made.
   - If sections like `template:` or `input_boolean:` already exist, append the new configurations below them without duplicating section names.

### 2. Entity IDs Update:
   - Update the entity IDs  (`calendar.x`, `calendar.y` ...) in `configuration.yaml` to match those of your Home Assistant calendars.

### 3. Script Setup:
   - Copy the `python_scripts` folder into your Home Assistant configuration directory. If a `python_scripts` folder already exists, transfer the `esp_calendar_data_conversion.py` file into it.

### 4. Calendar Name Adjustments:
   - If using multi-word calendar names, add these to the `CALENDAR_NAMES` list in `esp_calendar_data_conversion.py`, for example:
	 ```python
	 CALENDAR_NAMES = {"calendar.family_events": "Family Events", "calendar.work_events": "Work Events"}
	 ```

### 5. Home Assistant Restart:
   - Restart Home Assistant to apply the changes.

### 6. Adding your device to Home Assistant:
   - After the firmware is compiled and uploaded, and the Inkplate board is powered, add it to Home Assistant for data synchronization. It should be detected under `Settings -> Devices`.
