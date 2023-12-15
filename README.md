# another_mvg

Comming soon, another MVG Integration for Home Assistant



# Code for your configuration.yaml

### Add the name of this integration

To load the integration, you have to add

```  - platform: another_mvg``` **Required**

to the **sensor:** part in your configuration.

> [!CAUTION]
> Don't add the line ```sensor:``` a second time!
> If it is already there, just put ```  - platform: another_mvg``` below your other **platforms** in the sensor part.

### Define your station / stop / location
```   globalid: "de:09162:10"``` **Required**
> [!IMPORTANT]
> The station identifier of the stop/station/location. I decided to use the identifier, instead of names, because it is more clear (for the API) and leads to less problems.
The only problem you have, is to find the identifier (globalid) by your own.
Here you can find the globalid for your station.
> ```https://www.mvg.de/api/fib/v2/location?query=Pasing```
> Just replace the name in the query. If there is more than one entry, you have to find the correct one. I recommend to open the link on your PC/Notebook.



### Name of the table
```    name: "Pasing"``` **Optional, but strongly recommended**

Is the name of the table and will be used for the sensorname. It is **NOT** the name of the station for the API call.

### Minimal configuration example
```
sensor:
  - platform: another_mvg
    name: "Pasing"
    globalid: "de:09162:10"
```


```   hidedestination```

```   limit```

```   transporttypes```

```   doublestationnumber```

```   globalid2```

Show only some lines
```   onlyline: "S3,S4,S20"```

If you want to see only some lines, like S3, S4 and S20, you can configure it comma seperated.


Complex configuration example
```
sensor:
  - platform: another_mvg
    name: "Olching"
    globalid: "de:09179:6110"
    hidedestination: "Mammendorf,Maisach"
    limit: 15
    transporttypes: "SBAHN"
  - platform: another_mvg
    name: "Olching Busabfahrten"
    globalid: "de:09179:6110"
    hidedestination: "Graßlfing, Olchinger See;Olching, Georgenstraße"
    onlyline: "860,831,843"
    limit: 15
    transporttypes: "BUS,REGIONAL_BUS"
    doublestationnumber: "2"
  - platform: another_mvg
    name: "Eichenau"
    globalid: "de:09179:6180"
    hidedestination: "Geltendorf,Buchenau,Grafrath"
    limit: 15
  - platform: another_mvg
    name: "Eichenau Busabfahrten"
    globalid: "de:09179:6181"
    hidedestination: "Freiham (S) Süd"
    limit: 15
    transporttypes: "BUS,REGIONAL_BUS"
    onlyline: "860"
  - platform: another_mvg
    name: "Pasing"
    globalid: "de:09162:10"
    onlyline: "S3,S4,S20"
    limit: 20
    hidedestination: "Deisenhofen,Holzkirchen,Grafing Bahnhof, Trudering, Ostbahnhof,Haar,Ebersberg"
  - platform: another_mvg
    name: "Pasing - alle Abfahrten"
    globalid: "de:09162:10"
    limit: 20
    doublestationnumber: "2"
    transporttypes: "SBAHN,BUS,REGIONAL_BUS"
  - platform: another_mvg
    name: "Olching und Eichenau"
    globalid: "de:09179:6110"
    globalid2: "de:09179:6180"
    hidedestination: "Mammendorf,Maisach,Geltendorf,Buchenau,Grafrath"
    limit: 15
    transporttypes: "SBAHN"
    doublestationnumber: "3"
```

Browser View

![Screenshot_33](https://github.com/Nisbo/another_mvg/assets/26260572/c24cd351-2a44-4c5f-9250-5a4bb1f07450)

![Screenshot_34](https://github.com/Nisbo/another_mvg/assets/26260572/29985729-abfa-4049-8c4b-6b375303ceb1)

Mobile App View

![20231214_202848000_iOS](https://github.com/Nisbo/another_mvg/assets/26260572/17f56859-fe8c-440f-8168-dc491c42952e)

![20231214_202831000_iOS](https://github.com/Nisbo/another_mvg/assets/26260572/a461b67e-9871-45bd-b98d-27e255d2350c)
