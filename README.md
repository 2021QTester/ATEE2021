## ATEE2021

ATEE2021 is an automated testing tool for Android applications. Based on Q-testing, ATEE2021 employs an action equivalence evaluation engine to find and merge redundant actions with similar functions by exploiting both GUI appearance and functionscation under test.


## Installation

#### System Requirements

- Python: 2.7
- Android SDK: API 19-28 (make sure `adb` and `aapt` commands are available)
- Linux: Ubuntu 16.04-20.04

The above versions of software have been tested in our experiments. We use Pyinstalller to bundle the ATEE project into executable files which can be run in Linux.  You don't need to install the tool or any other python dependency; just download all the files will suffice. The application under test may be installed in a physical phone connected to a computer or in an Android virtual machine, of which API level 19 (4.4) and 28 (9.0) has been tested.

## Usage

The artifact of ATEE is shared with OneDrive, and can be downloaded [Here](https://1drv.ms/u/s!AmfV7AZ50ULTiT36goqVTvFpbqoJ?e=5Pybc6)


#### Settings

Before running ATEE, please create the **Config.txt** as follow: 

```
[Path]
#Note: The apks should be placed under 'Benchmark' directory.
Benchmark = /Users/Your_Name/Benchmark/
APK_NAME = your_app_under_test.apk

# For instrumented APKs
APP_SOURCE_PATH = /Users/Your_Name/Projects/test
MANIFEST_FILE = /Users/Your_Name/Projects/test/src/main/AndroidManifest.xml


[Setting]
# You can use command `adb devices` to get the Android device's ID replace the DEVICE_ID.
DEVICE_ID = emulator-5554
# You may change TIME_LIMIT for debug.
TIME_LIMIT = 3600
# You can specify the launchable Activity, if ATEE cannot find one.
ACTIVITY_NAME = 
```

#### Running

Run the application with the following bash command:

   ```shell
   ./main -r Config.txt
   ```

#### Output

The output contents are placed in folder `benchmark/<apk_name>_output-1/`

```
/event_output -- The structures and actionable events of each GUI screen.
/crash_log.txt -- Test results including the test cases and recorded crashes and exceptions.
```

BTW, it is often the norm that ATEE ends with an Import Error: it is a bug injected due to Pyinstalller.

