# NYC Life
Find essential life elements on the go in NYC: WiFi hotspots, subway entrances, and restrooms.

### Key features

1. Via Google Maps API, **display the places of interest** in a given area.
  - **Main navigation (category)** includes: *WiFi hotspots, subway entrances,* and *restrooms with public access*
  - **Clicking a category** item will update the place markers on the map accordingly
2. Detecting the current location, **indicate the accesses nearest** to the user.
3. **Clicking a place marker** on a map will reveal *the details about the venue*. (E.g. SSID for WiFi access, running trains for subway entrance, etc.)
4. User can **search by address or/and zip code** for planning trips in advance.
5. `ajax` call results are stored locally if user's browser supports `localStorage`, so that API calls don't have to be made every time user switches navigation.

---

### APIs Used

1. [**Google Maps API**](https://developers.google.com/maps/): display geolocation data on maps
2. [**NYC Open Data API**](https://data.cityofnewyork.us/): pull geolocation data source, from the end points below
  - WiFi Hotspots: https://data.cityofnewyork.us/resource/jd4g-ks2z.json
  - Subway Entrance: https://data.cityofnewyork.us/resource/he7q-3hwy.json

---

### Custom Data Set

Public Restrooms data from [NYC Open Data API](https://data.cityofnewyork.us/resource/h87e-shkn.json) only contains locations managed by city authorities (e.g. parks, playgrounds) and not commercial entities (e.g. Starbucks, McDonalds). More importantly, its geocode information isn't really usable as-is. For more useful interface, I collected NYC restroom data from a few online sources, geocoded each location, and created a JSON file. The resources used in the process include:

- **Restroom data**: [diaroogle.com](http://diaroogle.com/toilets), [toiletfinder.com](http://www.toiletfinder.com/), and [nyrestroom.com](http://m3.mappler.net/nyrestroom/))
- **Geocoder**: [geocod.io](https://geocod.io/)
- **CSV to JSON**: [csvjson.com](http://www.csvjson.com/csv2json)

---

### Limitations

- Data sets used, *whether provided by NYC Open Data or custom-created*, are **not** guaranteed to be up to date--especially with WiFi hotspots and restrooms. Storefronts change rapidly in New York City; entities listed here might not be there today, and/or new places will keep popping up constantly.
- Subway entrance info can come in handy when a given station has separate accesses to uptown/downtown trains, or/and multiple entry points. This feature *can be more useful* if it could actually visualize up-/downtown directions and running lines per entrance, but NYC Open Data API is not sophisticated enough to provide such details *yet*.
