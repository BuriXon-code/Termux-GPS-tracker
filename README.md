# Termux-GPS-tracker 📍🗺️

## About
The script is designed to track your current location and estimate the distance to a specified geographical point. Once you reach the target location, it alerts you with vibration and/or a sound signal.

The script utilizes the `termux-api` package to retrieve GPS coordinates, control device volume (during an alarm), and enable vibration. Additionally, it requires the `sox` package to generate a beep sound and `jq` for JSON parsing.

![screenshot](/img1.jpg)

## Installation
To install the script, execute:

```bash
git clone https://github.com/BuriXon-code/Termux-GPS-tracker
cd Termux-GPS-tracker
chmod +x tracker
```

## Usage
The script requires specific parameters:

- `-lt | --latitude <value>`  
  _(Required)_ Latitude of the target location, e.g., `-10.123`

- `-lg | --longitude <value>`  
  _(Required)_ Longitude of the target location, e.g., `50.765`

- `-r  | --radius <value>`  
  _(Required)_ Radius in meters to trigger the alert

- `-d  | --delay <value>`  
  _(Optional, default: 15)_ Delay in seconds between GPS checks

- `-p  | --provider <gps|network|passive>`  
  _(Optional, default: gps)_ The location provider method

- `-v  | --volume <value>`  
  _(Optional, default: 40)_ Alarm volume level (range: 1-150)

- `-s  | --save <path-to-file>`  
  _(Optional)_ Saves location tracking data to a **KML file**.

> [!CAUTION]
> If the file already exists, it will be **overwritten**.

>[!WARNING]
> The script opens the KML file upon startup, appends new waypoints after each measurement, and closes the KML document only when the script is stopped with CTRL+C. Stopping the script in any other way will result in file corruption.

> [!TIP]
> The saved KML file can be used in **Google Earth** or similar applications to visualize the traveled route.

### Usage example:
```bash
tracker -lt 12.34567 -lg 76.54321 -r 100 -d 60 -p network -v 100 -s /sdcard/route.kml
```
Or using an environment variable:
```bash
export LOCATION="-lt 12.34567 -lg 76.54321"
tracker $(echo $LOCATION) -r 100 -d 60 -p network -v 100 -s /sdcard/route.kml
```

![screenshot](/img2.jpg)

## Compatibility
For proper functionality, ensure the following packages are installed in Termux:
- **Termux:API** with `termux-api` package
- **bash**
- **sox** (for sound alerts)
- **jq** (for JSON parsing)

## Support
### Contact me:
For any issues, suggestions, or questions, reach out via:

- **Email:** support@burixon.com.pl  
- **Contact form:** [Click here](https://burixon.com.pl/kontakt.php)

### Support me:
If you find this script useful, consider supporting my work by making a donation:

[**DONATE HERE**](https://burixon.com.pl/donate/)

Your contributions help in developing new projects and improving existing tools!

---

Enjoy tracking with Termux-GPS-tracker! 🌍🛵
