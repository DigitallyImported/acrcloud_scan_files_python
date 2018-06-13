# [Audio Recognition](https://www.acrcloud.com/music-recognition) -- File Scan Tool (Python Script)

## Overview
  [ACRCloud](https://www.acrcloud.com/) provides [Automatic Content Recognition](https://www.acrcloud.com/docs/introduction/automatic-content-recognition/) services for [Audio Fingerprinting](https://www.acrcloud.com/docs/introduction/audio-fingerprinting/) based applications such as **[Audio Recognition](https://www.acrcloud.com/music-recognition)** (supports music, video, ads for both online and offline), **[Broadcast Monitoring](https://www.acrcloud.com/broadcast-monitoring)**, **[Second Screen](https://www.acrcloud.com/second-screen-synchronization)**, **[Copyright Protection](https://www.acrcloud.com/copyright-protection-de-duplication)** and etc.<br>
  
  This tool can scan audio/video files and detect audios you want to recognize such as music, ads.

  Supported Format:
  
>>Audio: mp3, wav, m4a, flac, aac, amr, ape, ogg ...<br>
>>Video: mp4, mkv, wmv, flv, ts, avi ...

## Requirements

- Python
- backports.csv
- requests
- Follow one of the tutorials to create a project and get your host, access_key and access_secret.

 * [How to identify songs by sound](https://www.acrcloud.com/docs/tutorials/identify-music-by-sound/)
 
 * [How to detect custom audio content by sound](https://www.acrcloud.com/docs/tutorials/identify-audio-custom-content/)
 

## Installation 
 
 For Windows System, you must install [Python](https://www.python.org/downloads/windows/) and [pip](https://pip.pypa.io/en/stable/installing/).
 
 Open your terminal and change to the script directory of <strong>acrcloud_scan_files_python-master</strong>. Then run the command: 
 
 ```
pip install -r requirements.txt
 ```
## Install ACRCloud Python SDK 
 

 You can run the following command to install it.

 ```
 python -m pip install git+https://github.com/acrcloud/acrcloud_sdk_python
 ```

 Or you can download the sdk and install it by following command.

 [ACRCloud Python SDK](https://github.com/acrcloud/acrcloud_sdk_python).


 ```
 sudo python setup.py install
 ```

## For Windows

### Install Library
 Windows Runtime Library
 
 X86: [download and install Library(windows/vcredist_x86.exe)](https://www.microsoft.com/en-us/download/details.aspx?id=5555)
 
 x64: [download and install Library(windows/vcredist_x64.exe)](https://www.microsoft.com/en-us/download/details.aspx?id=14632)

 
## Usage: 

        _    ____ ____   ____ _                 _
       / \  / ___|  _ \ / ___| | ___  _   _  __| |
      / _ \| |   | |_) | |   | |/ _ \| | | |/ _` |
     / ___ \ |___|  _ <| |___| | (_) | |_| | (_| |
    /_/   \_\____|_| \_\\____|_|\___/ \____|\____|
 
 Before you use this script,you must have acrcloud host,access_key and access_secret.
 If you haven't have these ,you can register one https://console.acrcloud.com/signup
 
 Change the content of config.json,fill in your host, access_key and access_secret
 ```
{
  "host": "xxxxx",
  "access_key": "xxxxx",
  "access_secret": "xxxxx"
}
 ```
 
 ```
 python acrcloud_scan_files_python.py -d folder_path
 python acrcloud_scan_files_python.py -f file_path
 python acrcloud_scan_files_python.py -h get_usage_help
 ```

### Scan Folder Example:
 ```
 python acrcloud_scan_files_python.py -d ~/music
 ```
### Scan File Example: 
 ```
 python acrcloud_scan_files_python.py -f ~/testfiles/test.mp3
 ```
 
## Add more params
"-s" ---- scan step. （The scan interval.）

"-r" ---- scan range. （The scan range.）

"-l" ---- use how many seconds to recongize.  (recongizing length)

"-c" ---- set the config file path.

"-w" ---- results with duration. (1-yes, 0-no), you must set offset config for your access key, pls contact support@acrcloud.com
 ```
 If you want to change scan interval or you want to set recognize range,you can add some params
 Example:
     python acrcloud_scan_files_python.py -f ~/testfiles/test.mp3 -s 30 -r 0-20
     python acrcloud_scan_files_python.py -d ~/music -s 30 -w 1
 ```
## Scan error_scan file

 ```
 When Scan program  occurs some errors,error detail will store in error_scan.txt,When the scan tasks are finished, you can rescan these error task.
 Example: 
    python acrcloud_scan_files_python.py -e error_scan.txt
 ```

Default is scan folder where this script in.

The results are saved in the folder where this script in.

