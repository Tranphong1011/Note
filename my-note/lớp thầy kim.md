api : nhận request từ client và trả về server
openweathermap : cung cấp api miễn phí 
pixapay: tải ảnh 
tênapi: 0935464872abcdef
keyapi: 96cc3806460f7d24b160b391745bbce0

https://openweathermap.org/current

api: theo thành phố:
`https://api.openweathermap.org/data/2.5/weather?q={city name}&appid=[{API key}]`

`https://api.openweathermap.org/data/2.5/weather?q=hanoi&appid=96cc3806460f7d24b160b391745bbce0`

`https://api.openweathermap.org/data/2.5/weather?q=seoul&units=metric&&appid={API%20KEY}`


thêm `&units=metric&` vào giữa tên thành phố sẽ chuyển nhiệt độ K sang độ C

bấm Alt+0176 để hiển thị °
Lấy tên thành phố, cho limit là 1
![](https://i.imgur.com/tmFJWdz.png)
Lấy kinh vĩ độ: https://www.latlong.net/
![](https://i.imgur.com/W6UUybU.png)
![](https://i.imgur.com/mBEi74q.png)
-   `coord`
    -   `coord.lon` City geo location, longitude
    -   `coord.lat` City geo location, latitude
-   `weather` (more info Weather condition codes)
    -   `weather.id` Weather condition id
    -   `weather.main` Group of weather parameters (Rain, Snow, Extreme etc.)
    -   `weather.description` Weather condition within the group. You can get the output in your language. [Learn more](https://openweathermap.org/current#multi)
    -   `weather.icon` Weather icon id
-   `base` Internal parameter
-   `main`
    -   `main.temp` Temperature. Unit Default: Kelvin, Metric: Celsius, Imperial: Fahrenheit.
    -   `main.feels_like` Temperature. This temperature parameter accounts for the human perception of weather. Unit Default: Kelvin, Metric: Celsius, Imperial: Fahrenheit.
    -   `main.pressure` Atmospheric pressure (on the sea level, if there is no sea_level or grnd_level data), hPa
    -   `main.humidity` Humidity, %
    -   `main.temp_min` Minimum temperature at the moment. This is minimal currently observed temperature (within large megalopolises and urban areas). Unit Default: Kelvin, Metric: Celsius, Imperial: Fahrenheit.
    -   `main.temp_max` Maximum temperature at the moment. This is maximal currently observed temperature (within large megalopolises and urban areas). Unit Default: Kelvin, Metric: Celsius, Imperial: Fahrenheit.
    -   `main.sea_level` Atmospheric pressure on the sea level, hPa
    -   `main.grnd_level` Atmospheric pressure on the ground level, hPa
-   `visibility` Visibility, meter. The maximum value of the visibility is 10km
-   `wind`
    -   `wind.speed` Wind speed. Unit Default: meter/sec, Metric: meter/sec, Imperial: miles/hour.
    -   `wind.deg` Wind direction, degrees (meteorological)
    -   `wind.gust` Wind gust. Unit Default: meter/sec, Metric: meter/sec, Imperial: miles/hour
-   `clouds`
    -   `clouds.all` Cloudiness, %
-   `rain`
    -   `rain.1h` Rain volume for the last 1 hour, mm
    -   `rain.3h` Rain volume for the last 3 hours, mm
-   `snow`
    -   `snow.1h` Snow volume for the last 1 hour, mm
    -   `snow.3h` Snow volume for the last 3 hours, mm
-   `dt` Time of data calculation, unix, UTC
-   `sys`
    -   `sys.type` Internal parameter
    -   `sys.id` Internal parameter
    -   `sys.message` Internal parameter
    -   `sys.country` Country code (GB, JP etc.)
    -   `sys.sunrise` Sunrise time, unix, UTC
    -   `sys.sunset` Sunset time, unix, UTC
-   `timezone` Shift in seconds from UTC
-   `id` City ID
-   `name` City name
-   `cod` Internal parameter


chú ý: cách add dữ liệu vô text trong js

![](https://i.imgur.com/aknQVKy.png)

`https://api.openweathermap.org/data/2.5/weather?q=${cityName}&units=metric&&appid=${key}`
`https://api.openweathermap.org/data/2.5/weather?q=${cityName}&units=metric&&appid=${key}`


https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=query&key=[YOUR_API_KEY

https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=query&key=AIzaSyDfmDQxtTCXca25PgHAu3YrlwnI-dGV2i4

https://developers.google.com/youtube/v3/docs/search/list?apix_params=%7B%22part%22%3A%5B%22snippet%22%5D%2C%22maxResults%22%3A30%2C%22q%22%3A%22black%20pink%22%7D#usage
part: snippet
q: tên muốn search
maxResults: 30 