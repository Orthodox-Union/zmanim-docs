### To Get Zmanim Info:  

Url: http://db.ou.org/zmanim/getCalendarData.php  
Parameters: mode, dateBegin, dateEnd, israel_holidays, candles_offset, havdala_offset, lat, lng, timezone, ical, csv, chametz_times

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>mode</td>
    <td>Specify the mode you want to use</td>
    <td>Use year, month, day, or drange</td>
  </tr>
  <tr>
    <td>dateBegin</td>
    <td>Specify begin date for drange mode, or day / month / year to use for other modes</td>
    <td>Date in M/D/Y format</td>
  </tr>
  <tr>
    <td>dateEnd</td>
    <td>Use only for drange mode to specify end date</td>
    <td>Date in M/D/Y format</td>
  </tr>
  <tr>
    <td>israel_holidays</td>
    <td>(optional) Specify if to use Israel holidays schedule or not</td>
    <td>Boolean true/false. Default: false</td>
  </tr>
  <tr>
    <td>candles_offset</td>
    <td>(optional) Specify amount of time before shkia candle lighting should be</td>
    <td>Number. Default: 18</td>
  </tr>
  <tr>
    <td>havdala_offset</td>
    <td>(optional) Specify amount of time after shkia havdala should be</td>
    <td>Number. Default: 42</td>
  </tr>
  <tr>
    <td>lat</td>
    <td>Latitude of the place being searched</td>
    <td>Long</td>
  </tr>
  <tr>
    <td>lng</td>
    <td>Longitude of the place being searched</td>
    <td>Long</td>
  </tr>
  <tr>
    <td>timezone</td>
    <td>Timezone of the place being searched</td>
    <td>Name of the timezone from Olson Database. Example: America/New_York</td>
  </tr>
  <tr>
    <td>ical</td>
    <td>(optional) Specify if output should be in iCal file</td>
    <td>Boolean true/false. Default: false</td>
  </tr>
  <tr>
    <td>csv</td>
    <td>(optional) Specify if output should be in csv file</td>
    <td>Boolean true/false. Default: false</td>
  </tr>
  <tr>
    <td>chametz_times</td>
    <td>(optional) Specify if to include latest times for eating and burning chametz</td>
    <td>Boolean true/false. Default: false</td>
  </tr>
</table>

Uses:
http://db.ou.org/zmanim/getCalendarData.php?mode=day&timezone=America/New_York&dateBegin=4/14/2014&lat=40.590034&lng=-73.940101


Returns:
JSON  
```json
{
   "engDateString":"4\/14\/2014",
   "hebDateString":"14 Nisan 5774",
   "dayOfWeek":"1",
   "zmanim":{
      "tzeis_850_degrees":"20:16:14",
      "sof_zman_tefila_gra":"10:43:49",
      "mincha_ketana_gra":"16:48:17",
      "tzeis_595_degrees":"20:01:59",
      "sof_zman_shema_gra":"09:37:33",
      "sof_zman_tefila_ma":"10:15:16",
      "sof_zman_shema_ma":"08:54:38",
      "mincha_gedola_ma":"13:29:29",
      "talis_ma":"05:27:00",
      "chatzos":"12:56:21",
      "tzeis_42_minutes":"20:15:57",
      "sunset":"19:33:57",
      "plag_mincha_ma":"18:11:07",
      "tzeis_72_minutes":"20:45:57",
      "sunrise":"06:18:44",
      "alos_ma":"04:52:44"
   },
   "candle_lighting":"19:15:00",
   "erev_yomtov":"First Day of Pesach",
   "dafYomi":{
      "masechta":"Beitzah",
      "daf":"15"
   },
   "specialShabbos":false,
   "parsha_shabbos":"Tzav",
   "candle_lighting_shabbos":"18:43:00"
}
```
### To Get Holiday Info:  

Url: http://db.ou.org/zmanim/getHolidayCalData.php  
Parameters: year, hebrewYear, israelHolidays, callback, php  

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>year</td>
    <td>(optional) Specify which year the holidays should be for</td>
    <td>YYYY format. Default: this year</td>
  </tr>
  <tr>
    <td>hebrewYear</td>
    <td>(optional) Specify the hebrew year for rosh chodesh information</td>
    <td>YYYY format. If specified, will return rosh chodesh information instead of holiday information</td>
  </tr>
  <tr>
    <td>israelHolidays</td>
    <td>(optional) Specify if to use Israel holidays schedule or not</td>
    <td>Boolean true/false. Default: false</td>
  </tr>
  <tr>
    <td>callback</td>
    <td>(optional) Used for jsonp response</td>
    <td>Function name. If none specified will return json string.</td>
  </tr>
  <tr>
    <td>php</td>
    <td>(optional) Specify if to return data as serialized php variable</td>
    <td>Boolean true/false. If not true will return json string.</td>
  </tr>
</table>

Uses:  
For Holiday Information:  
http://db.ou.org/zmanim/getHolidayCalData.php?year=2014&israelHolidays=true


Returns:
JSON  
```json 
[{
      "name":"TuBShevat",
      "workLvl":8,
      "dateYear1":"Thu Jan 16",
      "dateYear2":"Wed Feb 4"
   },
   {
      "name":"TaanitEsther",
      "workLvl":8,
      "dateYear1":"Thu Mar 13",
      "dateYear2":"Wed Mar 4"
   }, ...]
```
For Rosh Chodesh Information:  
http://db.ou.org/zmanim/getHolidayCalData.php?hebrewYear=5774

Returns:
JSON  
```json 
[{
      "EnglishDate":"March 31",
      "HebrewDate":"29 Adar II",
      "Molad":"3 hours, 54 minutes and 9 chalakim",
      "JewishMonth":"Nissan",
      "DayOfWeek":"Monday"
   },
   {
      "EnglishDate":"April 29",
      "HebrewDate":"29 Nissan",
      "Molad":"16 hours, 38 minutes and 10 chalakim",
      "JewishMonth":"Iyar",
      "DayOfWeek":"Tuesday"
   }, ...]
```  
### To Get Geographical Info:  

Url: http://db.ou.org/geoip  
Parameters: ip, country, city, region, term, limit, format, callback

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>ip</td>
    <td>(optional) Specify ip address</td>
    <td>Valid ip address</td>
  </tr>
  <tr>
    <td>country</td>
    <td>(optional) Specify country name</td>
    <td>Use 2-letter country code. Must specify if using city parameter.</td>
  </tr>
  <tr>
    <td>city</td>
    <td>(optional) Specify city name</td>
    <td>Must specify if using country parameter</td>
  </tr>
  <tr>
    <td>region</td>
    <td>(optional) Specify region(state) name</td>
    <td>Can be used with country and city options</td>
  </tr>
  <tr>
    <td>term</td>
    <td>(optional) Specify term to search for autocomplete data</td>
    <td>Mandatory to get autocomplete data. Can be used with limit parameter.</td>
  </tr>
  <tr>
    <td>limit</td>
    <td>(optional) Specify maximum amount of autocomplete data to return</td>
    <td>Number. To be used with term parameter.</td>
  </tr>
  <tr>
    <td>format</td>
    <td>(optional) Specify format results should be returned in</td>
    <td>Use php or json. Default: json</td>
  </tr>
  <tr>
    <td>callback</td>
    <td>(optional) Used for jsonp</td>
    <td>Function name. If none specified will return json string.</td>
  </tr>
</table>

Uses:  
For Geographical Information:  
http://db.ou.org/geoip/?country=US&city=monsey

Returns:
JSON  
```json
{
   "cc":"US",
   "rc":"NY",
   "cn":"Monsey",
   "pc":"10952",
   "latitude":"41.1181",
   "longitude":"-74.0833",
   "timezone":"America\/New_York"
}
```  
For Autocomplete Data:  
http://db.ou.org/geoip/?term=Mon&limit=5

Returns:
JSON  
```json
[
   "Mon Choisy, MU",
   "Mon Plaisir, BE",
   "Mon Plaisir, GD",
   "Mon Plaisir, TT",
   "Mon Repos, LC"
]
```
### To Get Location Info:  

Url: http://db.ou.org/location  
Parameters: ip, country, city, region, zipCode, legacy, format, callback

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>ip</td>
    <td>(optional) Specify ip address</td>
    <td>Valid ip address</td>
  </tr>
  <tr>
    <td>country</td>
    <td>(optional) Specify country name</td>
    <td>Use 2-letter country code. Must specify if using city parameter.</td>
  </tr>
  <tr>
    <td>city</td>
    <td>(optional) Specify city name</td>
    <td>Must specify if using country parameter</td>
  </tr>
  <tr>
    <td>region</td>
    <td>(optional) Specify region(state) name</td>
    <td>Can be used with country and city options</td>
  </tr>
  <tr>
    <td>zipCode</td>
    <td>(optional) Specify zip code</td>
    <td>Valid postal code in US or CA</td>
  </tr>
  <tr>
    <td>legacy</td>
    <td>(optional) Specify if to include certain legacy fields (country, region, city, today and hebrewYear)</td>
    <td>Use 1 for true.</td>
  </tr>
  <tr>
    <td>format</td>
    <td>(optional) Specify format results should be returned in</td>
    <td>Use php or json. Default: json</td>
  </tr>
  <tr>
    <td>callback</td>
    <td>(optional) Used for jsonp</td>
    <td>Function name. If none specified will return json string.</td>
  </tr>
</table>

Uses:  
http://db.ou.org/location/?city=Toronto&country=CA

Returns:
JSON  
```json
{
   "cc":"CA",
   "rc":"BC",
   "cn":"Toronto",
   "pc":"",
   "latitude":"43.6667",
   "longitude":"-79.4167",
   "timezone":"America\/Toronto",
   "date":"03\/12\/2014 09:58:14",
   "community_id":null,
   "israelHolidays":false,
   "candlesOffset":"18",
   "havdalaOffset":"42"
}
```  
### To Get Autocomplete Location Info:  

Url: http://db.ou.org/location/autocomplete.php  
Parameters: term, limit, format, callback

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>term</td>
    <td>Specify term to search for autocomplete data</td>
    <td>Any term</td>
  </tr>
  <tr>
    <td>limit</td>
    <td>(optional) Specify maximum amount of autocomplete data to return</td>
    <td>Number.</td>
  </tr>
  <tr>
    <td>format</td>
    <td>(optional) Specify format results should be returned in</td>
    <td>Use php or json. Default: json</td>
  </tr>
  <tr>
    <td>callback</td>
    <td>(optional) Used for jsonp</td>
    <td>Function name. If none specified will return json string.</td>
  </tr>
</table>

Uses:  
http://db.ou.org/location/autocomplete.php?term=san

Returns:
JSON  
```json
[
   "San , MX",
   "San Acacia, NM US",
   "San Adri, ES",
   "San Adria Del Bes, ES",
   "San Adrian, ES",
   "San Adri?n De Veiga, ES",
   "San Adri?n, ES",
   "San Agata, IT",
   "San Agust, AR",
   "San Agust, ES"
]
```  
### To Get Parsha Info:  

Url: http://db.ou.org/zmanim/getParshaData.php  
Parameters: date

<table>
  <tr>
    <th>Name</th><th>Description</th><th>Format</th>
  </tr>
  <tr>
    <td>date</td>
    <td>Specify date in week</td>
    <td>Date in M/D/Y format</td>
  </tr>
</table>

Uses:  
http://db.ou.org/zmanim/getParshaData.php?date=2/13/2015

Returns:
JSON  
```json
{
   "parsha" : "Mishpatim"
}
```  
