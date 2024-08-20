# Cyclist - Google DA Certificate Case Study
## Ask
The question is: How do annual members and casual riders use Cyclistic bikes differently?
## Prepare
The dataset I used due to limitation of memory: 2024-01
## Process
### Step 1:factor exploration
- Rider_id: identical so removed
- ride_type: catogorical data type/ can be used to calculate the percentage of users in each group
- started_at/ended_at:Time frame data type: can be used to calculate the riding duration and day of week, hour of day of riding, after calculating duration, ended_at dimension can be deleted.
- start_station_name/start_station_id/end_station_name/end_station_id: categorial data type/ there are a lot of places to start with and end with. I don't include the demographic analysis in this report so removed the fatcors.
- start_lat/start_lng/end_lat/end_lng:start and end latitude and longitude. Can be used to calcuate the displacement rid using distance formulae. After that, the four dimensions can be removed.
### Step 2: remove and create factors
- Rider_id removed
- Duration: ended_at - started_at -> format as seconds
- ended_at removed
- start_station_name	start_station_id	end_station_name	end_station_id removed
- Length = $`\sqrt{(startLat-endLat)^2+(startLng-endLng)^2}*111111`$ [one degree of movement in longtitude or latitude is equal to 111111 meters](https://gis.stackexchange.com/questions/5821/calculating-latitude-longitude-x-miles-from-point#:~:text=The%20northwards%20displacement%20is%20r,(latitude)%20%2F%20111111%20degrees.)
- start_lat	start_lng	end_lat	end_lng removed
