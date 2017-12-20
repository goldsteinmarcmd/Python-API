

```python
# Dependencies
import matplotlib.pyplot as plt
import requests as req
import pandas as pd
from citipy import citipy
from random import randint
import numpy as np
import seaborn as sns
import time
import json
api_key= '24f5204f68b4b9dc36478a8b73c9b19f'
url = 'http://api.openweathermap.org/data/2.5/weather'
```


```python
for data in range(1):
    rand_lat = randint(9, 10)
    rand_long = randint(19, 20)
    print(rand_lat)
    print(str(rand_long))
```


```python
# Some random coordinates
 # Query parameters can be set using a dictionary
params = {'appid': '24f5204f68b4b9dc36478a8b73c9b19f',
           'coord':{"lon":'rand_long',"lat":'rand_lat'}}
for data in range(1000):
    rand_lat = randint(-90,90)
    rand_long = randint(-180,180)
    print(rand_lat, rand_long)
    coordinates = [(rand_lat, rand_long)]
    query_url = url + '?appid=' + api_key + '&lat=' + str(rand_lat) + '&lon=' + str(rand_long)
    print(query_url)
    
    
    # Get weather data
    weather_response = req.get(query_url, params=params)
    weather_json = weather_response.json()

    print("The weather API responded with: ")
    print(json.dumps(weather_json, indent=4, sort_keys=True))
#     print()
#    # Query parameters can be set using a dictionary
#     params = {'appid': '24f5204f68b4b9dc36478a8b73c9b19f',
#              'coord':{"lon":'rand_long',"lat":'rand_lat'}}
    
    weather_data = []
```

    53 12
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=53&lon=12
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 90
        },
        "cod": 200,
        "coord": {
            "lat": 53,
            "lon": 12
        },
        "dt": 1512456600,
        "id": 2887842,
        "main": {
            "humidity": 93,
            "pressure": 1025,
            "temp": 280.15,
            "temp_max": 280.15,
            "temp_min": 280.15
        },
        "name": "Kletzke",
        "sys": {
            "country": "DE",
            "id": 4916,
            "message": 0.1647,
            "sunrise": 1512457712,
            "sunset": 1512485808,
            "type": 1
        },
        "visibility": 10000,
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 270,
            "speed": 5.7
        }
    }
    54 -13
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=54&lon=-13
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 54,
            "lon": -13
        },
        "dt": 1512457935,
        "id": 0,
        "main": {
            "grnd_level": 1040.36,
            "humidity": 100,
            "pressure": 1040.36,
            "sea_level": 1040.34,
            "temp": 284.798,
            "temp_max": 284.798,
            "temp_min": 284.798
        },
        "name": "",
        "sys": {
            "message": 0.1665,
            "sunrise": 1512464039,
            "sunset": 1512491484
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 204.504,
            "speed": 12.57
        }
    }
    -64 164
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-64&lon=164
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -64,
            "lon": 164
        },
        "dt": 1512457935,
        "id": 0,
        "main": {
            "grnd_level": 1006.56,
            "humidity": 97,
            "pressure": 1006.56,
            "sea_level": 1006.54,
            "temp": 273.198,
            "temp_max": 273.198,
            "temp_min": 273.198
        },
        "name": "",
        "sys": {
            "message": 0.1705,
            "sunrise": 1512398910,
            "sunset": 1512471775
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 269.004,
            "speed": 13.37
        }
    }
    31 44
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=31&lon=44
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 31,
            "lon": 44
        },
        "dt": 1512457936,
        "id": 98862,
        "main": {
            "grnd_level": 1003.73,
            "humidity": 66,
            "pressure": 1003.73,
            "sea_level": 1035.44,
            "temp": 282.898,
            "temp_max": 282.898,
            "temp_min": 282.898
        },
        "name": "Mu\u1e29\u0101faz\u0327at an Najaf",
        "sys": {
            "country": "IQ",
            "message": 0.1747,
            "sunrise": 1512445665,
            "sunset": 1512482498
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 211.504,
            "speed": 1.47
        }
    }
    -11 -66
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-11&lon=-66
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": -11,
            "lon": -66
        },
        "dt": 1512457936,
        "id": 3906466,
        "main": {
            "grnd_level": 1003.89,
            "humidity": 96,
            "pressure": 1003.89,
            "sea_level": 1021.5,
            "temp": 298.023,
            "temp_max": 298.023,
            "temp_min": 298.023
        },
        "name": "Riberalta",
        "sys": {
            "country": "BO",
            "message": 0.1647,
            "sunrise": 1512467561,
            "sunset": 1512513431
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 7.00366,
            "speed": 0.92
        }
    }
    9 82
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=9&lon=82
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": 9,
            "lon": 82
        },
        "dt": 1512457937,
        "id": 1226260,
        "main": {
            "grnd_level": 1023.02,
            "humidity": 100,
            "pressure": 1023.02,
            "sea_level": 1023.04,
            "temp": 300.098,
            "temp_max": 300.098,
            "temp_min": 300.098
        },
        "name": "Trincomalee",
        "sys": {
            "country": "LK",
            "message": 0.1642,
            "sunrise": 1512434037,
            "sunset": 1512475888
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 32.5037,
            "speed": 5.92
        }
    }
    10 29
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=10&lon=29
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 10,
            "lon": 29
        },
        "dt": 1512457937,
        "id": 380308,
        "main": {
            "grnd_level": 978.84,
            "humidity": 75,
            "pressure": 978.84,
            "sea_level": 1024.17,
            "temp": 293.773,
            "temp_max": 293.773,
            "temp_min": 293.773
        },
        "name": "Abyei",
        "sys": {
            "country": "SD",
            "message": 0.0033,
            "sunrise": 1512446862,
            "sunset": 1512488510
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 337.504,
            "speed": 3.97
        }
    }
    52 96
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=52&lon=96
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 52,
            "lon": 96
        },
        "dt": 1512457938,
        "id": 1489401,
        "main": {
            "grnd_level": 876.95,
            "humidity": 65,
            "pressure": 876.95,
            "sea_level": 1042.78,
            "temp": 266.448,
            "temp_max": 266.448,
            "temp_min": 266.448
        },
        "name": "Toora-Khem",
        "sys": {
            "country": "RU",
            "message": 0.1675,
            "sunrise": 1512437232,
            "sunset": 1512465956
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 265.004,
            "speed": 1.87
        }
    }
    -32 125
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-32&lon=125
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 100
        },
        "cod": 200,
        "coord": {
            "lat": -32,
            "lon": 125
        },
        "dt": 1512457938,
        "id": 7839503,
        "main": {
            "grnd_level": 1002.35,
            "humidity": 15,
            "pressure": 1002.35,
            "sea_level": 1020.24,
            "temp": 304.748,
            "temp_max": 304.748,
            "temp_min": 304.748
        },
        "name": "Dundas",
        "sys": {
            "country": "AU",
            "message": 0.1669,
            "sunrise": 1512419191,
            "sunset": 1512470104
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 336.504,
            "speed": 5.12
        }
    }
    -65 -113
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-65&lon=-113
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -65,
            "lon": -113
        },
        "dt": 1512457939,
        "id": 0,
        "main": {
            "grnd_level": 975.76,
            "humidity": 100,
            "pressure": 975.76,
            "sea_level": 975.78,
            "temp": 272.248,
            "temp_max": 272.248,
            "temp_min": 272.248
        },
        "name": "",
        "sys": {
            "message": 0.1749,
            "sunrise": 1512464000,
            "sunset": 1512539722
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 266.504,
            "speed": 21.42
        }
    }
    87 -96
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=87&lon=-96
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 87,
            "lon": -96
        },
        "dt": 1512457939,
        "id": 0,
        "main": {
            "grnd_level": 1036.39,
            "humidity": 84,
            "pressure": 1036.39,
            "sea_level": 1036.45,
            "temp": 260.848,
            "temp_max": 260.848,
            "temp_min": 260.848
        },
        "name": "",
        "sys": {
            "message": 0.1659,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 66.5037,
            "speed": 5.02
        }
    }
    -41 107
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-41&lon=107
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 24
        },
        "cod": 200,
        "coord": {
            "lat": -41,
            "lon": 107
        },
        "dt": 1512457940,
        "id": 0,
        "main": {
            "grnd_level": 1030.07,
            "humidity": 100,
            "pressure": 1030.07,
            "sea_level": 1030.21,
            "temp": 285.148,
            "temp_max": 285.148,
            "temp_min": 285.148
        },
        "name": "",
        "sys": {
            "message": 0.0046,
            "sunrise": 1512422012,
            "sunset": 1512475933
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 231.504,
            "speed": 9.82
        }
    }
    -31 -153
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-31&lon=-153
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -31,
            "lon": -153
        },
        "dt": 1512457940,
        "id": 0,
        "main": {
            "grnd_level": 1031.12,
            "humidity": 100,
            "pressure": 1031.12,
            "sea_level": 1031.14,
            "temp": 291.998,
            "temp_max": 291.998,
            "temp_min": 291.998
        },
        "name": "",
        "sys": {
            "message": 0.1663,
            "sunrise": 1512486057,
            "sunset": 1512536715
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01n",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 71.5037,
            "speed": 2.52
        }
    }
    -79 46
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-79&lon=46
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 8
        },
        "cod": 200,
        "coord": {
            "lat": -79,
            "lon": 46
        },
        "dt": 1512457941,
        "id": 0,
        "main": {
            "grnd_level": 617.96,
            "humidity": 70,
            "pressure": 617.96,
            "sea_level": 1019.07,
            "temp": 241.198,
            "temp_max": 241.198,
            "temp_min": 241.198
        },
        "name": "",
        "sys": {
            "message": 0.0049,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "02d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 189.004,
            "speed": 4.37
        }
    }
    -52 109
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-52&lon=109
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": -52,
            "lon": 109
        },
        "dt": 1512457941,
        "id": 0,
        "main": {
            "grnd_level": 1012.08,
            "humidity": 100,
            "pressure": 1012.08,
            "sea_level": 1012.17,
            "temp": 275.723,
            "temp_max": 275.723,
            "temp_min": 275.723
        },
        "name": "",
        "sys": {
            "message": 0.1699,
            "sunrise": 1512418824,
            "sunset": 1512478176
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 232.504,
            "speed": 12.07
        }
    }
    43 74
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=43&lon=74
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": 43,
            "lon": 74
        },
        "dt": 1512457942,
        "id": 1528913,
        "main": {
            "grnd_level": 977.63,
            "humidity": 92,
            "pressure": 977.63,
            "sea_level": 1048.69,
            "temp": 269.298,
            "temp_max": 269.298,
            "temp_min": 269.298
        },
        "name": "Ak-Su",
        "sys": {
            "country": "KG",
            "message": 0.2456,
            "sunrise": 1512440388,
            "sunset": 1512473367
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 287.504,
            "speed": 1.92
        }
    }
    54 -157
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=54&lon=-157
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 54,
            "lon": -157
        },
        "dt": 1512457942,
        "id": 0,
        "main": {
            "grnd_level": 1013.29,
            "humidity": 100,
            "pressure": 1013.29,
            "sea_level": 1013.31,
            "temp": 277.623,
            "temp_max": 277.623,
            "temp_min": 277.623
        },
        "name": "",
        "rain": {
            "3h": 0.17
        },
        "sys": {
            "message": 0.165,
            "sunrise": 1512498631,
            "sunset": 1512526033
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 248.504,
            "speed": 6.57
        }
    }
    -77 43
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-77&lon=43
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -77,
            "lon": 43
        },
        "dt": 1512457943,
        "id": 0,
        "main": {
            "grnd_level": 618.37,
            "humidity": 71,
            "pressure": 618.37,
            "sea_level": 1017.32,
            "temp": 241.098,
            "temp_max": 241.098,
            "temp_min": 241.098
        },
        "name": "",
        "sys": {
            "message": 0.1808,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 184.004,
            "speed": 5.47
        }
    }
    35 -107
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=35&lon=-107
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 75
        },
        "cod": 200,
        "coord": {
            "lat": 35,
            "lon": -107
        },
        "dt": 1512456900,
        "id": 5492450,
        "main": {
            "humidity": 13,
            "pressure": 1021,
            "temp": 274.64,
            "temp_max": 276.15,
            "temp_min": 273.15
        },
        "name": "South Valley",
        "sys": {
            "country": "US",
            "id": 1994,
            "message": 0.1655,
            "sunrise": 1512482496,
            "sunset": 1512518167,
            "type": 1
        },
        "visibility": 16093,
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 360,
            "speed": 3.1
        }
    }
    -38 -15
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-38&lon=-15
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -38,
            "lon": -15
        },
        "dt": 1512457944,
        "id": 0,
        "main": {
            "grnd_level": 1014.91,
            "humidity": 94,
            "pressure": 1014.91,
            "sea_level": 1015.01,
            "temp": 290.048,
            "temp_max": 290.048,
            "temp_min": 290.048
        },
        "name": "",
        "rain": {
            "3h": 0.185
        },
        "sys": {
            "message": 0.1676,
            "sunrise": 1512451838,
            "sunset": 1512504681
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 321.504,
            "speed": 12.32
        }
    }
    52 174
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=52&lon=174
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": 52,
            "lon": 174
        },
        "dt": 1512457945,
        "id": 0,
        "main": {
            "grnd_level": 1019.94,
            "humidity": 100,
            "pressure": 1019.94,
            "sea_level": 1020.36,
            "temp": 275.498,
            "temp_max": 275.498,
            "temp_min": 275.498
        },
        "name": "",
        "sys": {
            "message": 0.1665,
            "sunrise": 1512418495,
            "sunset": 1512447242
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 297.004,
            "speed": 12.42
        }
    }
    72 -9
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=72&lon=-9
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 48
        },
        "cod": 200,
        "coord": {
            "lat": 72,
            "lon": -9
        },
        "dt": 1512457945,
        "id": 7535941,
        "main": {
            "grnd_level": 1026.91,
            "humidity": 100,
            "pressure": 1026.91,
            "sea_level": 1027.05,
            "temp": 272.123,
            "temp_max": 272.123,
            "temp_min": 272.123
        },
        "name": "Olonkinbyen",
        "sys": {
            "country": "SJ",
            "message": 0.1662,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 347.004,
            "speed": 11.42
        }
    }
    -33 123
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-33&lon=123
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": -33,
            "lon": 123
        },
        "dt": 1512457946,
        "id": 2071858,
        "main": {
            "grnd_level": 988.97,
            "humidity": 21,
            "pressure": 988.97,
            "sea_level": 1019.15,
            "temp": 302.723,
            "temp_max": 302.723,
            "temp_min": 302.723
        },
        "name": "Esperance Shire",
        "sys": {
            "country": "AU",
            "message": 0.1638,
            "sunrise": 1512419523,
            "sunset": 1512470733
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 352.004,
            "speed": 4.22
        }
    }
    -25 -48
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-25&lon=-48
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -25,
            "lon": -48
        },
        "dt": 1512457946,
        "id": 3467609,
        "main": {
            "grnd_level": 1017.67,
            "humidity": 100,
            "pressure": 1017.67,
            "sea_level": 1026.36,
            "temp": 295.548,
            "temp_max": 295.548,
            "temp_min": 295.548
        },
        "name": "Cananeia",
        "rain": {
            "3h": 1.685
        },
        "sys": {
            "country": "BR",
            "message": 0.1673,
            "sunrise": 1512461657,
            "sunset": 1512510697
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 72.5037,
            "speed": 2.62
        }
    }
    -37 -110
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-37&lon=-110
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": -37,
            "lon": -110
        },
        "dt": 1512457947,
        "id": 0,
        "main": {
            "grnd_level": 1041.99,
            "humidity": 97,
            "pressure": 1041.99,
            "sea_level": 1041.97,
            "temp": 291.723,
            "temp_max": 291.723,
            "temp_min": 291.723
        },
        "name": "",
        "sys": {
            "message": 0.1684,
            "sunrise": 1512474808,
            "sunset": 1512527323
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 345.504,
            "speed": 2.82
        }
    }
    82 115
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=82&lon=115
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 36
        },
        "cod": 200,
        "coord": {
            "lat": 82,
            "lon": 115
        },
        "dt": 1512457947,
        "id": 0,
        "main": {
            "grnd_level": 1048.23,
            "humidity": 80,
            "pressure": 1048.23,
            "sea_level": 1048.17,
            "temp": 251.098,
            "temp_max": 251.098,
            "temp_min": 251.098
        },
        "name": "",
        "sys": {
            "message": 0.1663,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 203.504,
            "speed": 2.62
        }
    }
    -51 16
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-51&lon=16
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -51,
            "lon": 16
        },
        "dt": 1512457948,
        "id": 0,
        "main": {
            "grnd_level": 1033.8,
            "humidity": 96,
            "pressure": 1033.8,
            "sea_level": 1033.78,
            "temp": 275.473,
            "temp_max": 275.473,
            "temp_min": 275.473
        },
        "name": "",
        "sys": {
            "message": 0.1698,
            "sunrise": 1512441450,
            "sunset": 1512500201
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 349.004,
            "speed": 2.27
        }
    }
    -3 150
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-3&lon=150
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": -3,
            "lon": 150
        },
        "dt": 1512457949,
        "id": 2094342,
        "main": {
            "grnd_level": 1017.18,
            "humidity": 100,
            "pressure": 1017.18,
            "sea_level": 1017.49,
            "temp": 301.448,
            "temp_max": 301.448,
            "temp_min": 301.448
        },
        "name": "Kavieng",
        "rain": {
            "3h": 0.695
        },
        "sys": {
            "country": "PG",
            "message": 0.1664,
            "sunrise": 1512416519,
            "sunset": 1512460760
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 277.504,
            "speed": 6.92
        }
    }
    89 -107
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=89&lon=-107
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 89,
            "lon": -107
        },
        "dt": 1512457949,
        "id": 0,
        "main": {
            "grnd_level": 1039.47,
            "humidity": 87,
            "pressure": 1039.47,
            "sea_level": 1039.49,
            "temp": 256.973,
            "temp_max": 256.973,
            "temp_min": 256.973
        },
        "name": "",
        "sys": {
            "message": 0.1968,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 39.0037,
            "speed": 4.37
        }
    }
    -18 -26
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-18&lon=-26
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -18,
            "lon": -26
        },
        "dt": 1512457950,
        "id": 0,
        "main": {
            "grnd_level": 1028.61,
            "humidity": 100,
            "pressure": 1028.61,
            "sea_level": 1028.63,
            "temp": 295.948,
            "temp_max": 295.948,
            "temp_min": 295.948
        },
        "name": "",
        "rain": {
            "3h": 0.22
        },
        "sys": {
            "message": 0.1677,
            "sunrise": 1512457204,
            "sunset": 1512504584
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 72.0037,
            "speed": 2.62
        }
    }
    83 79
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=83&lon=79
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 83,
            "lon": 79
        },
        "dt": 1512457950,
        "id": 0,
        "main": {
            "grnd_level": 1042.23,
            "humidity": 71,
            "pressure": 1042.23,
            "sea_level": 1042.25,
            "temp": 252.498,
            "temp_max": 252.498,
            "temp_min": 252.498
        },
        "name": "",
        "sys": {
            "message": 0.0031,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 152.504,
            "speed": 5.77
        }
    }
    71 67
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=71&lon=67
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": 71,
            "lon": 67
        },
        "dt": 1512457950,
        "id": 0,
        "main": {
            "grnd_level": 1014.91,
            "humidity": 94,
            "pressure": 1014.91,
            "sea_level": 1015.99,
            "temp": 271.298,
            "temp_max": 271.298,
            "temp_min": 271.298
        },
        "name": "",
        "sys": {
            "message": 0.1654,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 213.004,
            "speed": 3.87
        }
    }
    28 77
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=28&lon=77
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 75
        },
        "cod": 200,
        "coord": {
            "lat": 28,
            "lon": 77
        },
        "dt": 1512455400,
        "id": 1261145,
        "main": {
            "humidity": 46,
            "pressure": 1016,
            "temp": 295.15,
            "temp_max": 295.15,
            "temp_min": 295.15
        },
        "name": "Nuh",
        "sys": {
            "country": "IN",
            "id": 7809,
            "message": 0.1662,
            "sunrise": 1512437347,
            "sunset": 1512474973,
            "type": 1
        },
        "visibility": 1000,
        "weather": [
            {
                "description": "smoke",
                "icon": "50d",
                "id": 711,
                "main": "Smoke"
            }
        ],
        "wind": {
            "deg": 290,
            "speed": 4.1
        }
    }
    -1 -91
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-1&lon=-91
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": -1,
            "lon": -91
        },
        "dt": 1512457952,
        "id": 3652694,
        "main": {
            "grnd_level": 1020.99,
            "humidity": 98,
            "pressure": 1020.99,
            "sea_level": 1024.82,
            "temp": 294.448,
            "temp_max": 294.448,
            "temp_min": 294.448
        },
        "name": "Puerto Villamil",
        "sys": {
            "country": "EC",
            "message": 0.1641,
            "sunrise": 1512474574,
            "sunset": 1512518418
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 127.004,
            "speed": 3.32
        }
    }
    64 143
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=64&lon=143
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 64,
            "lon": 143
        },
        "dt": 1512457952,
        "id": 2122311,
        "main": {
            "grnd_level": 917.24,
            "humidity": 0,
            "pressure": 917.24,
            "sea_level": 1039.21,
            "temp": 231.548,
            "temp_max": 231.548,
            "temp_min": 231.548
        },
        "name": "Oymyakon",
        "sys": {
            "country": "RU",
            "message": 0.0037,
            "sunrise": 1512431677,
            "sunset": 1512448938
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 287.004,
            "speed": 1.12
        }
    }
    -74 158
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-74&lon=158
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 48
        },
        "cod": 200,
        "coord": {
            "lat": -74,
            "lon": 158
        },
        "dt": 1512457952,
        "id": 0,
        "main": {
            "grnd_level": 757.55,
            "humidity": 94,
            "pressure": 757.55,
            "sea_level": 998.48,
            "temp": 255.623,
            "temp_max": 255.623,
            "temp_min": 255.623
        },
        "name": "",
        "sys": {
            "message": 0.1671,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 212.504,
            "speed": 2.57
        }
    }
    -18 -156
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-18&lon=-156
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": -18,
            "lon": -156
        },
        "dt": 1512457953,
        "id": 0,
        "main": {
            "grnd_level": 1024.88,
            "humidity": 100,
            "pressure": 1024.88,
            "sea_level": 1025.02,
            "temp": 298.648,
            "temp_max": 298.648,
            "temp_min": 298.648
        },
        "name": "",
        "rain": {
            "3h": 0.9275
        },
        "sys": {
            "message": 0.0028,
            "sunrise": 1512488409,
            "sunset": 1512535797
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 85.5037,
            "speed": 3.92
        }
    }
    21 24
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=21&lon=24
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 21,
            "lon": 24
        },
        "dt": 1512457953,
        "id": 0,
        "main": {
            "grnd_level": 953.71,
            "humidity": 59,
            "pressure": 953.71,
            "sea_level": 1032.81,
            "temp": 286.148,
            "temp_max": 286.148,
            "temp_min": 286.148
        },
        "name": "",
        "sys": {
            "message": 0.1652,
            "sunrise": 1512449235,
            "sunset": 1512488535
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 55.0037,
            "speed": 3.22
        }
    }
    50 -70
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=50&lon=-70
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": 50,
            "lon": -70
        },
        "dt": 1512457954,
        "id": 6137271,
        "main": {
            "grnd_level": 984.35,
            "humidity": 98,
            "pressure": 984.35,
            "sea_level": 1043.63,
            "temp": 265.798,
            "temp_max": 265.798,
            "temp_min": 265.798
        },
        "name": "Saguenay/Lac-Saint-Jean",
        "sys": {
            "country": "CA",
            "message": 0.1651,
            "sunrise": 1512476550,
            "sunset": 1512506343
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 138.004,
            "speed": 3.67
        }
    }
    17 21
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=17&lon=21
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 20
        },
        "cod": 200,
        "coord": {
            "lat": 17,
            "lon": 21
        },
        "dt": 1512457954,
        "id": 0,
        "main": {
            "grnd_level": 976.41,
            "humidity": 50,
            "pressure": 976.41,
            "sea_level": 1028.63,
            "temp": 290.623,
            "temp_max": 290.623,
            "temp_min": 290.623
        },
        "name": "",
        "sys": {
            "message": 0.1645,
            "sunrise": 1512449514,
            "sunset": 1512489697
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 51.5037,
            "speed": 4.77
        }
    }
    90 -136
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=90&lon=-136
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 68
        },
        "cod": 200,
        "coord": {
            "lat": 90,
            "lon": -136
        },
        "dt": 1512457955,
        "id": 0,
        "main": {
            "grnd_level": 1040.61,
            "humidity": 79,
            "pressure": 1040.61,
            "sea_level": 1040.71,
            "temp": 256.648,
            "temp_max": 256.648,
            "temp_min": 256.648
        },
        "name": "",
        "sys": {
            "message": 0.1928,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 352.004,
            "speed": 3.22
        }
    }
    63 -67
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=63&lon=-67
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": 63,
            "lon": -67
        },
        "dt": 1512457955,
        "id": 5983720,
        "main": {
            "grnd_level": 1012.73,
            "humidity": 100,
            "pressure": 1012.73,
            "sea_level": 1032.68,
            "temp": 266.598,
            "temp_max": 266.598,
            "temp_min": 266.598
        },
        "name": "Iqaluit",
        "sys": {
            "country": "CA",
            "message": 0.004,
            "sunrise": 1512481367,
            "sunset": 1512500079
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 316.504,
            "speed": 4.92
        }
    }
    90 -121
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=90&lon=-121
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 68
        },
        "cod": 200,
        "coord": {
            "lat": 90,
            "lon": -121
        },
        "dt": 1512457956,
        "id": 0,
        "main": {
            "grnd_level": 1040.61,
            "humidity": 79,
            "pressure": 1040.61,
            "sea_level": 1040.71,
            "temp": 256.648,
            "temp_max": 256.648,
            "temp_min": 256.648
        },
        "name": "",
        "sys": {
            "message": 0.1828,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 6.50366,
            "speed": 3.22
        }
    }
    -69 180
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-69&lon=180
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -69,
            "lon": 180
        },
        "dt": 1512457956,
        "id": 0,
        "main": {
            "grnd_level": 997.32,
            "humidity": 100,
            "pressure": 997.32,
            "sea_level": 997.38,
            "temp": 272.148,
            "temp_max": 272.148,
            "temp_min": 272.148
        },
        "name": "",
        "sys": {
            "message": 0.1654,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 30.5037,
            "speed": 5.32
        }
    }
    -74 23
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-74&lon=23
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 56
        },
        "cod": 200,
        "coord": {
            "lat": -74,
            "lon": 23
        },
        "dt": 1512457957,
        "id": 0,
        "main": {
            "grnd_level": 648.2,
            "humidity": 92,
            "pressure": 648.2,
            "sea_level": 1004.88,
            "temp": 249.398,
            "temp_max": 249.398,
            "temp_min": 249.398
        },
        "name": "",
        "sys": {
            "message": 0.1718,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 80.5037,
            "speed": 5.32
        }
    }
    -74 58
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-74&lon=58
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 12
        },
        "cod": 200,
        "coord": {
            "lat": -74,
            "lon": 58
        },
        "dt": 1512457957,
        "id": 0,
        "main": {
            "grnd_level": 720.02,
            "humidity": 86,
            "pressure": 720.02,
            "sea_level": 1005.73,
            "temp": 246.098,
            "temp_max": 246.098,
            "temp_min": 246.098
        },
        "name": "",
        "sys": {
            "message": 0.1716,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 201.504,
            "speed": 7.07
        }
    }
    -30 -30
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-30&lon=-30
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -30,
            "lon": -30
        },
        "dt": 1512457958,
        "id": 0,
        "main": {
            "grnd_level": 1029.1,
            "humidity": 100,
            "pressure": 1029.1,
            "sea_level": 1029.12,
            "temp": 291.648,
            "temp_max": 291.648,
            "temp_min": 291.648
        },
        "name": "",
        "rain": {
            "3h": 0.32
        },
        "sys": {
            "message": 0.1673,
            "sunrise": 1512456677,
            "sunset": 1512507038
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 168.004,
            "speed": 7.52
        }
    }
    -23 91
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-23&lon=91
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": -23,
            "lon": 91
        },
        "dt": 1512457959,
        "id": 0,
        "main": {
            "grnd_level": 1029.1,
            "humidity": 100,
            "pressure": 1029.1,
            "sea_level": 1029.08,
            "temp": 294.623,
            "temp_max": 294.623,
            "temp_min": 294.623
        },
        "name": "",
        "sys": {
            "message": 0.2488,
            "sunrise": 1512428540,
            "sunset": 1512477075
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 114.504,
            "speed": 8.17
        }
    }
    14 12
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=14&lon=12
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 14,
            "lon": 12
        },
        "dt": 1512457959,
        "id": 2441447,
        "main": {
            "grnd_level": 990.35,
            "humidity": 39,
            "pressure": 990.35,
            "sea_level": 1027.74,
            "temp": 287.523,
            "temp_max": 287.523,
            "temp_min": 287.523
        },
        "name": "Maine-Soroa",
        "sys": {
            "country": "NE",
            "message": 0.1663,
            "sunrise": 1512451356,
            "sunset": 1512492177
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 16.5037,
            "speed": 4.92
        }
    }
    -7 -93
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-7&lon=-93
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 20
        },
        "cod": 200,
        "coord": {
            "lat": -7,
            "lon": -93
        },
        "dt": 1512457960,
        "id": 0,
        "main": {
            "grnd_level": 1025.13,
            "humidity": 100,
            "pressure": 1025.13,
            "sea_level": 1025.19,
            "temp": 294.498,
            "temp_max": 294.498,
            "temp_min": 294.498
        },
        "name": "",
        "sys": {
            "message": 0.2427,
            "sunrise": 1512474453,
            "sunset": 1512519501
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02n",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 130.004,
            "speed": 6.92
        }
    }
    -45 26
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-45&lon=26
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 24
        },
        "cod": 200,
        "coord": {
            "lat": -45,
            "lon": 26
        },
        "dt": 1512457960,
        "id": 0,
        "main": {
            "grnd_level": 1039.31,
            "humidity": 100,
            "pressure": 1039.31,
            "sea_level": 1039.45,
            "temp": 280.623,
            "temp_max": 280.623,
            "temp_min": 280.623
        },
        "name": "",
        "sys": {
            "message": 0.0035,
            "sunrise": 1512440617,
            "sunset": 1512496223
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 236.004,
            "speed": 7.02
        }
    }
    3 143
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=3&lon=143
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 20
        },
        "cod": 200,
        "coord": {
            "lat": 3,
            "lon": 143
        },
        "dt": 1512457961,
        "id": 0,
        "main": {
            "grnd_level": 1017.83,
            "humidity": 100,
            "pressure": 1017.83,
            "sea_level": 1017.85,
            "temp": 302.123,
            "temp_max": 302.123,
            "temp_min": 302.123
        },
        "name": "",
        "sys": {
            "message": 0.1666,
            "sunrise": 1512418793,
            "sunset": 1512461845
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 311.004,
            "speed": 3.22
        }
    }
    8 -8
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=8&lon=-8
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": 8,
            "lon": -8
        },
        "dt": 1512457961,
        "id": 2595304,
        "main": {
            "grnd_level": 961.09,
            "humidity": 98,
            "pressure": 961.09,
            "sea_level": 1025.02,
            "temp": 291.773,
            "temp_max": 291.773,
            "temp_min": 291.773
        },
        "name": "Pr\u00e9fecture de Lola",
        "sys": {
            "country": "GN",
            "message": 0.1683,
            "sunrise": 1512455543,
            "sunset": 1512497594
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 227.504,
            "speed": 1.17
        }
    }
    -6 -91
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-6&lon=-91
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -6,
            "lon": -91
        },
        "dt": 1512457962,
        "id": 0,
        "main": {
            "grnd_level": 1024.8,
            "humidity": 100,
            "pressure": 1024.8,
            "sea_level": 1024.86,
            "temp": 294.523,
            "temp_max": 294.523,
            "temp_min": 294.523
        },
        "name": "",
        "sys": {
            "message": 0.1675,
            "sunrise": 1512474074,
            "sunset": 1512518920
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 138.004,
            "speed": 6.52
        }
    }
    -39 154
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-39&lon=154
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -39,
            "lon": 154
        },
        "dt": 1512457962,
        "id": 0,
        "main": {
            "grnd_level": 1022.77,
            "humidity": 97,
            "pressure": 1022.77,
            "sea_level": 1022.79,
            "temp": 293.498,
            "temp_max": 293.498,
            "temp_min": 293.498
        },
        "name": "",
        "rain": {
            "3h": 0.175
        },
        "sys": {
            "message": 0.1649,
            "sunrise": 1512411104,
            "sunset": 1512464272
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 65.0037,
            "speed": 7.82
        }
    }
    -65 -160
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-65&lon=-160
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 36
        },
        "cod": 200,
        "coord": {
            "lat": -65,
            "lon": -160
        },
        "dt": 1512457963,
        "id": 0,
        "main": {
            "grnd_level": 996.03,
            "humidity": 99,
            "pressure": 996.03,
            "sea_level": 996.13,
            "temp": 270.798,
            "temp_max": 270.798,
            "temp_min": 270.798
        },
        "name": "",
        "sys": {
            "message": 0.1699,
            "sunrise": 1512475258,
            "sunset": 1512551030
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 142.504,
            "speed": 4.47
        }
    }
    26 -167
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=26&lon=-167
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 12
        },
        "cod": 200,
        "coord": {
            "lat": 26,
            "lon": -167
        },
        "dt": 1512457963,
        "id": 0,
        "main": {
            "grnd_level": 1036.72,
            "humidity": 100,
            "pressure": 1036.72,
            "sea_level": 1036.78,
            "temp": 294.948,
            "temp_max": 294.948,
            "temp_min": 294.948
        },
        "name": "",
        "sys": {
            "message": 0.1647,
            "sunrise": 1512495686,
            "sunset": 1512533790
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02n",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 35.0037,
            "speed": 12.22
        }
    }
    -37 59
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-37&lon=59
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 48
        },
        "cod": 200,
        "coord": {
            "lat": -37,
            "lon": 59
        },
        "dt": 1512457964,
        "id": 0,
        "main": {
            "grnd_level": 1028.69,
            "humidity": 96,
            "pressure": 1028.69,
            "sea_level": 1028.75,
            "temp": 290.148,
            "temp_max": 290.148,
            "temp_min": 290.148
        },
        "name": "",
        "sys": {
            "message": 0.1717,
            "sunrise": 1512434249,
            "sunset": 1512486738
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 296.504,
            "speed": 8.12
        }
    }
    -56 -91
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-56&lon=-91
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -56,
            "lon": -91
        },
        "dt": 1512457964,
        "id": 0,
        "main": {
            "grnd_level": 1002.51,
            "humidity": 96,
            "pressure": 1002.51,
            "sea_level": 1002.49,
            "temp": 279.848,
            "temp_max": 279.848,
            "temp_min": 279.848
        },
        "name": "",
        "rain": {
            "3h": 0.475
        },
        "sys": {
            "message": 0.1658,
            "sunrise": 1512465327,
            "sunset": 1512527712
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 283.004,
            "speed": 11.02
        }
    }
    88 -159
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=88&lon=-159
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 48
        },
        "cod": 200,
        "coord": {
            "lat": 88,
            "lon": -159
        },
        "dt": 1512457965,
        "id": 0,
        "main": {
            "grnd_level": 1040.45,
            "humidity": 76,
            "pressure": 1040.45,
            "sea_level": 1040.47,
            "temp": 253.723,
            "temp_max": 253.723,
            "temp_min": 253.723
        },
        "name": "",
        "sys": {
            "message": 0.1661,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 4.50366,
            "speed": 4.22
        }
    }
    14 118
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=14&lon=118
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 14,
            "lon": 118
        },
        "dt": 1512457965,
        "id": 0,
        "main": {
            "grnd_level": 1023.02,
            "humidity": 100,
            "pressure": 1023.02,
            "sea_level": 1023.04,
            "temp": 299.373,
            "temp_max": 299.373,
            "temp_min": 299.373
        },
        "name": "",
        "rain": {
            "3h": 3.545
        },
        "sys": {
            "message": 0.1648,
            "sunrise": 1512425906,
            "sunset": 1512466732
        },
        "weather": [
            {
                "description": "moderate rain",
                "icon": "10d",
                "id": 501,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 26.0037,
            "speed": 7.07
        }
    }
    -15 39
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-15&lon=39
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 40
        },
        "cod": 200,
        "coord": {
            "lat": -15,
            "lon": 39
        },
        "dt": 1512453600,
        "id": 1033354,
        "main": {
            "humidity": 69,
            "pressure": 1016,
            "temp": 300.15,
            "temp_max": 300.15,
            "temp_min": 300.15
        },
        "name": "Prov\u00edncia de Nampula",
        "sys": {
            "country": "MZ",
            "id": 6856,
            "message": 0.1658,
            "sunrise": 1512441932,
            "sunset": 1512488647,
            "type": 1
        },
        "visibility": 10000,
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 40,
            "speed": 2.1
        }
    }
    53 57
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=53&lon=57
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 68
        },
        "cod": 200,
        "coord": {
            "lat": 53,
            "lon": 57
        },
        "dt": 1512457967,
        "id": 488618,
        "main": {
            "grnd_level": 983.87,
            "humidity": 83,
            "pressure": 983.87,
            "sea_level": 1042.65,
            "temp": 266.773,
            "temp_max": 266.773,
            "temp_min": 266.773
        },
        "name": "Starosubkhangulovo",
        "sys": {
            "country": "RU",
            "message": 0.1666,
            "sunrise": 1512446902,
            "sunset": 1512475011
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 194.004,
            "speed": 3.67
        }
    }
    -40 -20
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-40&lon=-20
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 36
        },
        "cod": 200,
        "coord": {
            "lat": -40,
            "lon": -20
        },
        "dt": 1512457967,
        "id": 0,
        "main": {
            "grnd_level": 1012.89,
            "humidity": 100,
            "pressure": 1012.89,
            "sea_level": 1012.99,
            "temp": 284.948,
            "temp_max": 284.948,
            "temp_min": 284.948
        },
        "name": "",
        "sys": {
            "message": 0.1672,
            "sunrise": 1512452678,
            "sunset": 1512506243
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 257.504,
            "speed": 17.62
        }
    }
    -60 -6
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-60&lon=-6
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -60,
            "lon": -6
        },
        "dt": 1512457968,
        "id": 0,
        "main": {
            "grnd_level": 1004.13,
            "humidity": 95,
            "pressure": 1004.13,
            "sea_level": 1004.19,
            "temp": 272.648,
            "temp_max": 272.648,
            "temp_min": 272.648
        },
        "name": "",
        "sys": {
            "message": 0.1637,
            "sunrise": 1512442906,
            "sunset": 1512509342
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 33.5037,
            "speed": 7.27
        }
    }
    -27 -77
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-27&lon=-77
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -27,
            "lon": -77
        },
        "dt": 1512457968,
        "id": 0,
        "main": {
            "grnd_level": 1028.45,
            "humidity": 100,
            "pressure": 1028.45,
            "sea_level": 1028.51,
            "temp": 289.273,
            "temp_max": 289.273,
            "temp_min": 289.273
        },
        "name": "",
        "sys": {
            "message": 0.1671,
            "sunrise": 1512468362,
            "sunset": 1512517918
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 171.504,
            "speed": 5.37
        }
    }
    -71 -68
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-71&lon=-68
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": -71,
            "lon": -68
        },
        "dt": 1512457969,
        "id": 0,
        "main": {
            "grnd_level": 951.44,
            "humidity": 89,
            "pressure": 951.44,
            "sea_level": 985.95,
            "temp": 271.248,
            "temp_max": 271.248,
            "temp_min": 271.248
        },
        "name": "",
        "sys": {
            "message": 0.1728,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 358.004,
            "speed": 4.97
        }
    }
    62 -173
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=62&lon=-173
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": 62,
            "lon": -173
        },
        "dt": 1512457970,
        "id": 0,
        "main": {
            "grnd_level": 1005.43,
            "humidity": 100,
            "pressure": 1005.43,
            "sea_level": 1005.41,
            "temp": 273.623,
            "temp_max": 273.623,
            "temp_min": 273.623
        },
        "name": "",
        "sys": {
            "message": 0.1663,
            "sunrise": 1512506148,
            "sunset": 1512526194
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 352.504,
            "speed": 9.57
        }
    }
    -68 -124
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-68&lon=-124
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 88
        },
        "cod": 200,
        "coord": {
            "lat": -68,
            "lon": -124
        },
        "dt": 1512457970,
        "id": 0,
        "main": {
            "grnd_level": 976.41,
            "humidity": 95,
            "pressure": 976.41,
            "sea_level": 976.43,
            "temp": 271.948,
            "temp_max": 271.948,
            "temp_min": 271.948
        },
        "name": "",
        "sys": {
            "message": 0.1704,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 214.004,
            "speed": 7.67
        }
    }
    5 -121
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=5&lon=-121
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 5,
            "lon": -121
        },
        "dt": 1512457971,
        "id": 0,
        "main": {
            "grnd_level": 1023.91,
            "humidity": 100,
            "pressure": 1023.91,
            "sea_level": 1023.89,
            "temp": 298.348,
            "temp_max": 298.348,
            "temp_min": 298.348
        },
        "name": "",
        "sys": {
            "message": 0.1691,
            "sunrise": 1512482372,
            "sunset": 1512525022
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 153.004,
            "speed": 5.82
        }
    }
    77 -61
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=77&lon=-61
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 56
        },
        "cod": 200,
        "coord": {
            "lat": 77,
            "lon": -61
        },
        "dt": 1512457971,
        "id": 0,
        "main": {
            "grnd_level": 905.48,
            "humidity": 81,
            "pressure": 905.48,
            "sea_level": 1040.63,
            "temp": 256.148,
            "temp_max": 256.148,
            "temp_min": 256.148
        },
        "name": "",
        "sys": {
            "message": 0.1717,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 130.504,
            "speed": 5.57
        }
    }
    -29 -152
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-29&lon=-152
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -29,
            "lon": -152
        },
        "dt": 1512457972,
        "id": 0,
        "main": {
            "grnd_level": 1030.31,
            "humidity": 100,
            "pressure": 1030.31,
            "sea_level": 1030.41,
            "temp": 293.598,
            "temp_max": 293.598,
            "temp_min": 293.598
        },
        "name": "",
        "sys": {
            "message": 0.0063,
            "sunrise": 1512486097,
            "sunset": 1512536195
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01n",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 61.0037,
            "speed": 5.27
        }
    }
    -33 -122
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-33&lon=-122
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 32
        },
        "cod": 200,
        "coord": {
            "lat": -33,
            "lon": -122
        },
        "dt": 1512457972,
        "id": 0,
        "main": {
            "grnd_level": 1034.77,
            "humidity": 96,
            "pressure": 1034.77,
            "sea_level": 1034.79,
            "temp": 293.398,
            "temp_max": 293.398,
            "temp_min": 293.398
        },
        "name": "",
        "sys": {
            "message": 0.1647,
            "sunrise": 1512478324,
            "sunset": 1512529565
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 11.0037,
            "speed": 6.97
        }
    }
    76 -111
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=76&lon=-111
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": 76,
            "lon": -111
        },
        "dt": 1512457973,
        "id": 0,
        "main": {
            "grnd_level": 1029.34,
            "humidity": 75,
            "pressure": 1029.34,
            "sea_level": 1030.01,
            "temp": 253.798,
            "temp_max": 253.798,
            "temp_min": 253.798
        },
        "name": "",
        "sys": {
            "message": 0.1672,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 170.504,
            "speed": 6.22
        }
    }
    75 -73
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=75&lon=-73
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": 75,
            "lon": -73
        },
        "dt": 1512457973,
        "id": 0,
        "main": {
            "grnd_level": 1036.31,
            "humidity": 90,
            "pressure": 1036.31,
            "sea_level": 1036.37,
            "temp": 260.998,
            "temp_max": 260.998,
            "temp_min": 260.998
        },
        "name": "",
        "sys": {
            "message": 0.0058,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 73.0037,
            "speed": 3.77
        }
    }
    -57 123
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-57&lon=123
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": -57,
            "lon": 123
        },
        "dt": 1512457974,
        "id": 0,
        "main": {
            "grnd_level": 1000.81,
            "humidity": 100,
            "pressure": 1000.81,
            "sea_level": 1000.87,
            "temp": 275.198,
            "temp_max": 275.198,
            "temp_min": 275.198
        },
        "name": "",
        "sys": {
            "message": 0.1638,
            "sunrise": 1512413552,
            "sunset": 1512476742
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 321.004,
            "speed": 7.32
        }
    }
    -32 92
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-32&lon=92
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 68
        },
        "cod": 200,
        "coord": {
            "lat": -32,
            "lon": 92
        },
        "dt": 1512457974,
        "id": 0,
        "main": {
            "grnd_level": 1035.83,
            "humidity": 100,
            "pressure": 1035.83,
            "sea_level": 1035.85,
            "temp": 290.948,
            "temp_max": 290.948,
            "temp_min": 290.948
        },
        "name": "",
        "sys": {
            "message": 0.1684,
            "sunrise": 1512427111,
            "sunset": 1512478028
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 113.504,
            "speed": 5.47
        }
    }
    17 133
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=17&lon=133
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 17,
            "lon": 133
        },
        "dt": 1512457975,
        "id": 0,
        "main": {
            "grnd_level": 1021.4,
            "humidity": 100,
            "pressure": 1021.4,
            "sea_level": 1021.42,
            "temp": 299.523,
            "temp_max": 299.523,
            "temp_min": 299.523
        },
        "name": "",
        "rain": {
            "3h": 2.915
        },
        "sys": {
            "message": 0.1774,
            "sunrise": 1512422623,
            "sunset": 1512462813
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 30.0037,
            "speed": 4.67
        }
    }
    0 120
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=0&lon=120
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 56
        },
        "cod": 200,
        "coord": {
            "lat": 0,
            "lon": 120
        },
        "dt": 1512457975,
        "id": 1633034,
        "main": {
            "grnd_level": 1007.29,
            "humidity": 89,
            "pressure": 1007.29,
            "sea_level": 1020.2,
            "temp": 302.848,
            "temp_max": 302.848,
            "temp_min": 302.848
        },
        "name": "Palu",
        "sys": {
            "country": "ID",
            "message": 0.1685,
            "sunrise": 1512424019,
            "sunset": 1512467664
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 280.504,
            "speed": 4.22
        }
    }
    53 -121
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=53&lon=-121
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 53,
            "lon": -121
        },
        "dt": 1512457976,
        "id": 5893064,
        "main": {
            "grnd_level": 889.68,
            "humidity": 86,
            "pressure": 889.68,
            "sea_level": 1050.84,
            "temp": 267.448,
            "temp_max": 267.448,
            "temp_min": 267.448
        },
        "name": "Barkerville",
        "sys": {
            "country": "CA",
            "message": 0.1663,
            "sunrise": 1512489661,
            "sunset": 1512517718
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 242.504,
            "speed": 0.52
        }
    }
    4 157
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=4&lon=157
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 4,
            "lon": 157
        },
        "dt": 1512457976,
        "id": 0,
        "main": {
            "grnd_level": 1017.59,
            "humidity": 100,
            "pressure": 1017.59,
            "sea_level": 1017.61,
            "temp": 301.148,
            "temp_max": 301.148,
            "temp_min": 301.148
        },
        "name": "",
        "sys": {
            "message": 0.1725,
            "sunrise": 1512415531,
            "sunset": 1512458384
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 96.0037,
            "speed": 6.52
        }
    }
    54 -27
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=54&lon=-27
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 54,
            "lon": -27
        },
        "dt": 1512457977,
        "id": 0,
        "main": {
            "grnd_level": 1023.67,
            "humidity": 92,
            "pressure": 1023.67,
            "sea_level": 1023.69,
            "temp": 283.348,
            "temp_max": 283.348,
            "temp_min": 283.348
        },
        "name": "",
        "rain": {
            "3h": 0.64
        },
        "sys": {
            "message": 0.1703,
            "sunrise": 1512467402,
            "sunset": 1512494843
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 187.504,
            "speed": 4.12
        }
    }
    -68 -109
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-68&lon=-109
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": -68,
            "lon": -109
        },
        "dt": 1512457977,
        "id": 0,
        "main": {
            "grnd_level": 963.2,
            "humidity": 94,
            "pressure": 963.2,
            "sea_level": 963.34,
            "temp": 271.898,
            "temp_max": 271.898,
            "temp_min": 271.898
        },
        "name": "",
        "sys": {
            "message": 0.0055,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 351.004,
            "speed": 2.57
        }
    }
    -79 -45
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-79&lon=-45
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -79,
            "lon": -45
        },
        "dt": 1512457978,
        "id": 0,
        "main": {
            "grnd_level": 937.26,
            "humidity": 58,
            "pressure": 937.26,
            "sea_level": 998.48,
            "temp": 253.623,
            "temp_max": 253.623,
            "temp_min": 253.623
        },
        "name": "",
        "sys": {
            "message": 0.1646,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 309.504,
            "speed": 1.07
        }
    }
    -7 127
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-7&lon=127
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": -7,
            "lon": 127
        },
        "dt": 1512457978,
        "id": 0,
        "main": {
            "grnd_level": 1018.15,
            "humidity": 100,
            "pressure": 1018.15,
            "sea_level": 1018.26,
            "temp": 302.848,
            "temp_max": 302.848,
            "temp_min": 302.848
        },
        "name": "",
        "sys": {
            "message": 0.1637,
            "sunrise": 1512421640,
            "sunset": 1512466683
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 266.004,
            "speed": 3.87
        }
    }
    7 -110
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=7&lon=-110
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 100
        },
        "cod": 200,
        "coord": {
            "lat": 7,
            "lon": -110
        },
        "dt": 1512457979,
        "id": 0,
        "main": {
            "grnd_level": 1023.75,
            "humidity": 100,
            "pressure": 1023.75,
            "sea_level": 1023.89,
            "temp": 297.698,
            "temp_max": 297.698,
            "temp_min": 297.698
        },
        "name": "",
        "rain": {
            "3h": 2.74
        },
        "sys": {
            "message": 0.1656,
            "sunrise": 1512479931,
            "sunset": 1512522181
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 207.504,
            "speed": 4.32
        }
    }
    49 -9
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=49&lon=-9
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": 49,
            "lon": -9
        },
        "dt": 1512457979,
        "id": 0,
        "main": {
            "grnd_level": 1049.44,
            "humidity": 100,
            "pressure": 1049.44,
            "sea_level": 1049.54,
            "temp": 284.598,
            "temp_max": 284.598,
            "temp_min": 284.598
        },
        "name": "",
        "sys": {
            "message": 0.1642,
            "sunrise": 1512461641,
            "sunset": 1512491964
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04n",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 192.504,
            "speed": 6.22
        }
    }
    -74 -142
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-74&lon=-142
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": -74,
            "lon": -142
        },
        "dt": 1512457980,
        "id": 0,
        "main": {
            "grnd_level": 987.19,
            "humidity": 89,
            "pressure": 987.19,
            "sea_level": 987.21,
            "temp": 268.273,
            "temp_max": 268.273,
            "temp_min": 268.273
        },
        "name": "",
        "sys": {
            "message": 0.1706,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 216.004,
            "speed": 5.82
        }
    }
    7 93
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=7&lon=93
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 76
        },
        "cod": 200,
        "coord": {
            "lat": 7,
            "lon": 93
        },
        "dt": 1512457981,
        "id": 0,
        "main": {
            "grnd_level": 1019.94,
            "humidity": 100,
            "pressure": 1019.94,
            "sea_level": 1019.88,
            "temp": 299.373,
            "temp_max": 299.373,
            "temp_min": 299.373
        },
        "name": "",
        "rain": {
            "3h": 6.22
        },
        "sys": {
            "message": 0.1686,
            "sunrise": 1512431195,
            "sunset": 1512473449
        },
        "weather": [
            {
                "description": "moderate rain",
                "icon": "10d",
                "id": 501,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 130.504,
            "speed": 9.67
        }
    }
    1 60
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=1&lon=60
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 32
        },
        "cod": 200,
        "coord": {
            "lat": 1,
            "lon": 60
        },
        "dt": 1512457982,
        "id": 0,
        "main": {
            "grnd_level": 1025.04,
            "humidity": 100,
            "pressure": 1025.04,
            "sea_level": 1025.06,
            "temp": 299.773,
            "temp_max": 299.773,
            "temp_min": 299.773
        },
        "name": "",
        "rain": {
            "3h": 0.67
        },
        "sys": {
            "message": 0.1877,
            "sunrise": 1512438522,
            "sunset": 1512481969
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 305.504,
            "speed": 4.52
        }
    }
    41 -33
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=41&lon=-33
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 32
        },
        "cod": 200,
        "coord": {
            "lat": 41,
            "lon": -33
        },
        "dt": 1512457982,
        "id": 0,
        "main": {
            "grnd_level": 1021.07,
            "humidity": 95,
            "pressure": 1021.07,
            "sea_level": 1021.17,
            "temp": 291.098,
            "temp_max": 291.098,
            "temp_min": 291.098
        },
        "name": "",
        "sys": {
            "message": 0.1653,
            "sunrise": 1512465712,
            "sunset": 1512499420
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03n",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 241.004,
            "speed": 12.77
        }
    }
    31 31
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=31&lon=31
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": 31,
            "lon": 31
        },
        "dt": 1512457983,
        "id": 350376,
        "main": {
            "grnd_level": 1032.02,
            "humidity": 83,
            "pressure": 1032.02,
            "sea_level": 1033.01,
            "temp": 285.348,
            "temp_max": 285.348,
            "temp_min": 285.348
        },
        "name": "Qutur",
        "sys": {
            "country": "EG",
            "message": 0.1647,
            "sunrise": 1512448787,
            "sunset": 1512485619
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 242.004,
            "speed": 1.67
        }
    }
    -70 -115
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-70&lon=-115
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 80
        },
        "cod": 200,
        "coord": {
            "lat": -70,
            "lon": -115
        },
        "dt": 1512457983,
        "id": 0,
        "main": {
            "grnd_level": 966.93,
            "humidity": 94,
            "pressure": 966.93,
            "sea_level": 966.94,
            "temp": 272.648,
            "temp_max": 272.648,
            "temp_min": 272.648
        },
        "name": "",
        "sys": {
            "message": 0.1694,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 119.004,
            "speed": 8.07
        }
    }
    -30 139
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-30&lon=139
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -30,
            "lon": 139
        },
        "dt": 1512457984,
        "id": 2067335,
        "main": {
            "grnd_level": 980.22,
            "humidity": 32,
            "pressure": 980.22,
            "sea_level": 1021.86,
            "temp": 298.798,
            "temp_max": 298.798,
            "temp_min": 298.798
        },
        "name": "Lyndhurst",
        "sys": {
            "country": "AU",
            "message": 0.0036,
            "sunrise": 1512416115,
            "sunset": 1512466456
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 223.004,
            "speed": 3.22
        }
    }
    -71 -23
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-71&lon=-23
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 68
        },
        "cod": 200,
        "coord": {
            "lat": -71,
            "lon": -23
        },
        "dt": 1512457984,
        "id": 0,
        "main": {
            "grnd_level": 998.05,
            "humidity": 100,
            "pressure": 998.05,
            "sea_level": 998.11,
            "temp": 266.698,
            "temp_max": 266.698,
            "temp_min": 266.698
        },
        "name": "",
        "sys": {
            "message": 0.1638,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 208.004,
            "speed": 2.02
        }
    }
    -47 173
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-47&lon=173
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -47,
            "lon": 173
        },
        "dt": 1512457985,
        "id": 0,
        "main": {
            "grnd_level": 1030.72,
            "humidity": 97,
            "pressure": 1030.72,
            "sea_level": 1030.78,
            "temp": 287.398,
            "temp_max": 287.398,
            "temp_min": 287.398
        },
        "name": "",
        "sys": {
            "message": 0.1726,
            "sunrise": 1512404873,
            "sunset": 1512461390
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04d",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 239.504,
            "speed": 4.37
        }
    }
    -44 -84
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-44&lon=-84
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -44,
            "lon": -84
        },
        "dt": 1512457985,
        "id": 0,
        "main": {
            "grnd_level": 1035.58,
            "humidity": 100,
            "pressure": 1035.58,
            "sea_level": 1035.56,
            "temp": 283.973,
            "temp_max": 283.973,
            "temp_min": 283.973
        },
        "name": "",
        "rain": {
            "3h": 0.13
        },
        "sys": {
            "message": 0.0073,
            "sunrise": 1512467235,
            "sunset": 1512522419
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 255.004,
            "speed": 5.12
        }
    }
    -72 70
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-72&lon=70
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 44
        },
        "cod": 200,
        "coord": {
            "lat": -72,
            "lon": 70
        },
        "dt": 1512457985,
        "id": 0,
        "main": {
            "grnd_level": 953.23,
            "humidity": 99,
            "pressure": 953.23,
            "sea_level": 994.14,
            "temp": 268.498,
            "temp_max": 268.498,
            "temp_min": 268.498
        },
        "name": "",
        "sys": {
            "message": 0.1649,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 50.0037,
            "speed": 2.62
        }
    }
    -87 58
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-87&lon=58
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 36
        },
        "cod": 200,
        "coord": {
            "lat": -87,
            "lon": 58
        },
        "dt": 1512457986,
        "id": 0,
        "main": {
            "grnd_level": 664.17,
            "humidity": 85,
            "pressure": 664.17,
            "sea_level": 1014.41,
            "temp": 245.348,
            "temp_max": 245.348,
            "temp_min": 245.348
        },
        "name": "",
        "sys": {
            "message": 0.1653,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "scattered clouds",
                "icon": "03d",
                "id": 802,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 242.004,
            "speed": 2.97
        }
    }
    77 -156
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=77&lon=-156
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 56
        },
        "cod": 200,
        "coord": {
            "lat": 77,
            "lon": -156
        },
        "dt": 1512457987,
        "id": 0,
        "main": {
            "grnd_level": 1033.15,
            "humidity": 92,
            "pressure": 1033.15,
            "sea_level": 1033.25,
            "temp": 258.623,
            "temp_max": 258.623,
            "temp_min": 258.623
        },
        "name": "",
        "sys": {
            "message": 0.1719,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "broken clouds",
                "icon": "04d",
                "id": 803,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 13.5037,
            "speed": 5.67
        }
    }
    77 -4
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=77&lon=-4
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 24
        },
        "cod": 200,
        "coord": {
            "lat": 77,
            "lon": -4
        },
        "dt": 1512457987,
        "id": 0,
        "main": {
            "grnd_level": 1026.67,
            "humidity": 100,
            "pressure": 1026.67,
            "sea_level": 1026.85,
            "temp": 270.523,
            "temp_max": 270.523,
            "temp_min": 270.523
        },
        "name": "",
        "sys": {
            "message": 0.1677,
            "sunrise": 0,
            "sunset": 0
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02d",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 358.004,
            "speed": 15.12
        }
    }
    -1 28
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-1&lon=28
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 0
        },
        "cod": 200,
        "coord": {
            "lat": -1,
            "lon": 28
        },
        "dt": 1512457988,
        "id": 212731,
        "main": {
            "grnd_level": 909.05,
            "humidity": 83,
            "pressure": 909.05,
            "sea_level": 1024.58,
            "temp": 295.748,
            "temp_max": 295.748,
            "temp_min": 295.748
        },
        "name": "Kisangani",
        "sys": {
            "country": "CD",
            "message": 0.1671,
            "sunrise": 1512446006,
            "sunset": 1512489850
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "01d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 152.004,
            "speed": 1.77
        }
    }
    -51 163
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-51&lon=163
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 8
        },
        "cod": 200,
        "coord": {
            "lat": -51,
            "lon": 163
        },
        "dt": 1512457988,
        "id": 0,
        "main": {
            "grnd_level": 1033.15,
            "humidity": 100,
            "pressure": 1033.15,
            "sea_level": 1033.17,
            "temp": 281.898,
            "temp_max": 281.898,
            "temp_min": 281.898
        },
        "name": "",
        "sys": {
            "message": 0.1724,
            "sunrise": 1512406181,
            "sunset": 1512464890
        },
        "weather": [
            {
                "description": "clear sky",
                "icon": "02d",
                "id": 800,
                "main": "Clear"
            }
        ],
        "wind": {
            "deg": 173.004,
            "speed": 2.77
        }
    }
    28 160
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=28&lon=160
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 20
        },
        "cod": 200,
        "coord": {
            "lat": 28,
            "lon": 160
        },
        "dt": 1512457989,
        "id": 0,
        "main": {
            "grnd_level": 1030.48,
            "humidity": 94,
            "pressure": 1030.48,
            "sea_level": 1030.54,
            "temp": 298.198,
            "temp_max": 298.198,
            "temp_min": 298.198
        },
        "name": "",
        "sys": {
            "message": 0.1654,
            "sunrise": 1512417417,
            "sunset": 1512455052
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02n",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 175.004,
            "speed": 7.27
        }
    }
    52 -36
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=52&lon=-36
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": 52,
            "lon": -36
        },
        "dt": 1512457989,
        "id": 0,
        "main": {
            "grnd_level": 1020.83,
            "humidity": 98,
            "pressure": 1020.83,
            "sea_level": 1020.85,
            "temp": 281.698,
            "temp_max": 281.698,
            "temp_min": 281.698
        },
        "name": "",
        "rain": {
            "3h": 0.18
        },
        "sys": {
            "message": 0.1707,
            "sunrise": 1512468940,
            "sunset": 1512497627
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10n",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 21.5037,
            "speed": 7.97
        }
    }
    -20 -179
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-20&lon=-179
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -20,
            "lon": -179
        },
        "dt": 1512457990,
        "id": 0,
        "main": {
            "grnd_level": 1021.23,
            "humidity": 100,
            "pressure": 1021.23,
            "sea_level": 1021.25,
            "temp": 299.373,
            "temp_max": 299.373,
            "temp_min": 299.373
        },
        "name": "",
        "sys": {
            "message": 0.1695,
            "sunrise": 1512493702,
            "sunset": 1512541549
        },
        "weather": [
            {
                "description": "overcast clouds",
                "icon": "04n",
                "id": 804,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 142.504,
            "speed": 2.72
        }
    }
    -35 157
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-35&lon=157
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 92
        },
        "cod": 200,
        "coord": {
            "lat": -35,
            "lon": 157
        },
        "dt": 1512457991,
        "id": 0,
        "main": {
            "grnd_level": 1022.53,
            "humidity": 100,
            "pressure": 1022.53,
            "sea_level": 1022.51,
            "temp": 293.973,
            "temp_max": 293.973,
            "temp_min": 293.973
        },
        "name": "",
        "rain": {
            "3h": 1.39
        },
        "sys": {
            "message": 0.1729,
            "sunrise": 1512411056,
            "sunset": 1512462877
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 42.0037,
            "speed": 10.97
        }
    }
    58 10
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=58&lon=10
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 24
        },
        "cod": 200,
        "coord": {
            "lat": 58,
            "lon": 10
        },
        "dt": 1512457991,
        "id": 2620279,
        "main": {
            "grnd_level": 1026.26,
            "humidity": 98,
            "pressure": 1026.26,
            "sea_level": 1026.44,
            "temp": 282.148,
            "temp_max": 282.148,
            "temp_min": 282.148
        },
        "name": "Hirtshals",
        "sys": {
            "country": "DK",
            "message": 0.1676,
            "sunrise": 1512460037,
            "sunset": 1512484441
        },
        "weather": [
            {
                "description": "few clouds",
                "icon": "02n",
                "id": 801,
                "main": "Clouds"
            }
        ],
        "wind": {
            "deg": 274.504,
            "speed": 13.17
        }
    }
    -15 30
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=-15&lon=30
    The weather API responded with: 
    {
        "base": "stations",
        "clouds": {
            "all": 64
        },
        "cod": 200,
        "coord": {
            "lat": -15,
            "lon": 30
        },
        "dt": 1512457992,
        "id": 895949,
        "main": {
            "grnd_level": 953.31,
            "humidity": 83,
            "pressure": 953.31,
            "sea_level": 1026,
            "temp": 296.623,
            "temp_max": 296.623,
            "temp_min": 296.623
        },
        "name": "Republic of Zambia",
        "rain": {
            "3h": 2.51
        },
        "sys": {
            "country": "ZM",
            "message": 0.1648,
            "sunrise": 1512444092,
            "sunset": 1512490808
        },
        "weather": [
            {
                "description": "light rain",
                "icon": "10d",
                "id": 500,
                "main": "Rain"
            }
        ],
        "wind": {
            "deg": 103.504,
            "speed": 1.52
        }
    }
    54 -133
    http://api.openweathermap.org/data/2.5/weather?appid=24f5204f68b4b9dc36478a8b73c9b19f&lat=54&lon=-133



```python
# Temperature (F) vs. Latitude

# Create lists of longitudes and atmospheric pressures
lat_data = []
pressure_data = []
temp_data = []
for data in weather_data:
    lat_data.append(data['coord']['lat'])
    pressure_data.append(data['main']['pressure'])
    temp_data.append(data["main"]["temp"])
# Shortcut:
# lon_data = [data['coord']['lon'] for data in weather_data]
# pressure_data = [data['main']['pressure'] for data in weather_data]

weather_dict = {'pressure': pressure_data, 'lat': lat_data, 'temp': temp_data}
weather_data_df = pd.DataFrame(weather_dict)
print(weather_data_df.head())
```


```python
# Build a scatter plot for each data type
plt.scatter(weather_data_df['lat'], weather_data_df['temp'], marker='o')

# Incorporate the other graph properties
plt.title('Temp vs Latitude')
plt.ylabel('Temperature')
plt.xlabel('Latitude')
plt.grid(True)

# Save the figure
plt.savefig('TempVsLat.png')

# Show plot
plt.show()
```


![png](output_4_0.png)



```python
# Humidity (%) vs. Latitude

lat_data = []
humidity_data = []

for data in weather_data:
    lat_data.append(data['coord']['lat'])
    humidity_data.append(data["main"]["humidity"])
# Shortcut:
# lon_data = [data['coord']['lon'] for data in weather_data]
# pressure_data = [data['main']['pressure'] for data in weather_data]

weather_dict = {'lat': lat_data, 'humidity': humidity_data}
weather_data_df = pd.DataFrame(weather_dict)
print(weather_data_df.head())

# Build a scatter plot for each data type
plt.scatter(weather_data_df['lat'], weather_data_df['humidity'], marker='o')

# Incorporate the other graph properties
plt.title('Humidity vs Latitude')
plt.ylabel('Humidity')
plt.xlabel('Latitude')
plt.grid(True)

# Save the figure
plt.savefig('HumidityVsLat.png')

# Show plot
plt.show()
```

       humidity    lat
    0        87  51.51
    1       100  48.85
    2         8  36.17
    3        80  59.33
    4        93 -33.87



![png](output_5_1.png)



```python
# Cloudiness (%) vs. Latitude
lat_data = []
clouds_data = []

for data in weather_data:
    lat_data.append(data['coord']['lat'])
    clouds_data.append(data["clouds"]["all"])
# Shortcut:
# lon_data = [data['coord']['lon'] for data in weather_data]
# pressure_data = [data['main']['pressure'] for data in weather_data]

weather_dict = {'lat': lat_data, 'all': clouds_data}
weather_data_df = pd.DataFrame(weather_dict)
print(weather_data_df.head())

# Build a scatter plot for each data type
plt.scatter(weather_data_df['lat'], weather_data_df['all'], marker='o')

# Incorporate the other graph properties
plt.title('Cloudiness vs Latitude')
plt.ylabel('Cloudiness')
plt.xlabel('Latitude')
plt.grid(True)

# Save the figure
plt.savefig('CloudinessVsLat.png')

# Show plot
plt.show()
```

       all    lat
    0    8  51.51
    1   90  48.85
    2    0  36.17
    3    8  59.33
    4   75 -33.87



![png](output_6_1.png)



```python
# Wind Speed (mph) vs. Latitude

lat_data = []
wind_data = []

for data in weather_data:
    lat_data.append(data['coord']['lat'])
    wind_data.append(data["wind"]["speed"])
# Shortcut:
# lon_data = [data['coord']['lon'] for data in weather_data]
# pressure_data = [data['main']['pressure'] for data in weather_data]

weather_dict = {'lat': lat_data, 'speed': wind_data}
weather_data_df = pd.DataFrame(weather_dict)
print(weather_data_df.head())

# Build a scatter plot for each data type
plt.scatter(weather_data_df['lat'], weather_data_df['speed'], marker='o')

# Incorporate the other graph properties
plt.title('Windspeed vs Latitude')
plt.ylabel('Windspeed')
plt.xlabel('Latitude')
plt.grid(True)

# Save the figure
plt.savefig('WindspeedVsLat.png')

# Show plot
plt.show()
```

         lat  speed
    0  51.51    2.6
    1  48.85    1.5
    2  36.17    6.7
    3  59.33    3.1
    4 -33.87   10.3



![png](output_7_1.png)



```python
# Loop through the list of cities and perform a request for data on each
for city in cities:
    # Get weather data
    params['coord'] = city
    response = req.get(url, params=params).json()
    weather_data.append(response)

print(weather_data)
```
