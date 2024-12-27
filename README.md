# Termux-GPS-tracker 📍🗺️
## About ...
The script is used to estimate your distance from the co -directed geographical place, and after reaching your destination, it informs you about this vibration and/or a sound signal.

The script uses the Termux-Uap package to download the current location and switch the volume of the device (during the alarm) and vibration. In addition, the required package is SOX, which allows you to make a beeping sound.

![screenshot](/img1.jpg)

## Installation ...

To install the script, perform:

```
git clone https://github.com/BuriXon-code/Termux-GPS-tracker
cd Termux-GPS-tracker
chmod +x tracker
```

## Usage ...

The script requires parameters, which are:
+ -lt | --latitude \<value, e.g. -10.123\> \(required!\)
+ -lg | --longitude \<value, e.g. 50.765\> \(required!\)
+ -r  | --radius \<value in meters\> \(required!\)
+ -d  | --delay \<value in seconds\> \(optional, 15 by default\)
+ -p  | --provider \<gps|network|passive\> \(optional, gps by default\)
+ -v  | --volume \<value in 1..150\> \(optional, 40 by default\)

**Usage example:**

```
tracker -lt 12.34567 -lg 76.54321 -r 100 -d 60 -p network -v 100
```
or
```
export LOCATION="-lt 12.34567 -lg 76.54321"
tracker $(echo $LOCATION) -r 100 -d 60 -p network -v 100
```

## Compatibility ...

The script for proper operation requires installed and configured Termux:API together with the termux-api package, Bash package, access to location, installed sox and jq package.

![screenshot](/img2.jpg)

In case of errors/problems with the script, let me know: **support@burixon.com.pl**.
