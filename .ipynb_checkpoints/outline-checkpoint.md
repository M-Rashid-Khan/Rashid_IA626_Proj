# ADS-B Exchange Data Analysis - 

## Introduction:
For this Project as `IA626 Big Data Course`, I worked on the `ADS-B Exchange` Aircraft tracking data. Initially I have used three textfiles for `NY-USA` for ADS-B Data. Transponder systems such as ADS-B [(Automatic Dependent Surveillance-Broadcast)](https://globe.adsbexchange.com/) is equipped in aircraft. Around seventy percent of commericial aircraft use this system. This system records the information which can be used to retrieve key values such as aircraft speed, latitude, longitude, vertical speed, altitude, many more. 

## Loading Libraries Required

```python

import json
import pandas as pd
import matplotlib.pyplot as plt

```


## Method to read the text files

There are number of files so, I created a method to read file, convert it to json format and append it to dictionary. Dictionaries are easy to process and efficiently processed in python. 

```python

def data_extraction(file):
    f = open(file,"r")
#     n=0
    data = []
    #convert each line to dictionary and append it to list of dictionaries
    for line in f:
        dic = json.loads(line)
        data.append(dic)
#         if n > 100:
#             break
#         n+=1
    return data

```



Different keys represent following information: 
  hex (String optional)
  flight (String optional - name of plane)
  alt_baro (int optional - altitude)
  alt_geom (int optional) 
  track (int optional)
  baro_rate (int optional)
  category (string optional)
  nav_qnh (float optional)
  nav_altitude_mcp (int optional)
  nav_heading (float optional)
  nic (int optional)
  rc (int optional)
  seen_pos (float optional)
  version (int optional)
  nic_baro (int optional)
  nac_p (int optional)
  nac_v (int optional)
  sil (int optional) 
  sil_type (string optional)
  mlat (array optional)
  tisb (array optional)
  messages (int optional)
  seen (float optional)
  rssi (float optional)  
  squawk (optional) - look at # conversion 7600, 7700, 4000, 5000, 7777, 6100, 5400, 4399, 4478, ...)
  speed (optional)
  mach (optional speed, mac to mph *767)
  emergency (optional string)
  lat (long optional)
  lon (long optional)
 
 
 
