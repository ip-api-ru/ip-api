# IP API: максимальная информация об IP-адресе (Geolocation)

###### Версия API

- 3.0 (от 20 июня 2019 года).

###### HTTPS/HTTP

- Поддержка HTTPS осуществляется через адрес https://ssl.ip-api.ru/;
- Поддержка HTTP осуществляется через адрес http://nossl.ip-api.ru/.

###### Ключи

- Обязательным ключем является apiKey - Ваш уникальный API-ключ для доступа к сервису;
- IP API поддерживает следующие ключи, с которыми можно делать запросы: query (конкретный IP-адрес), proxy, info и project;
- Ключ query может содержать IP-адрес или домен. Ключ query можно не использовать в запросе, если требуется информация об IP-адресе, с которого был сделан запрос;
- Ключ proxy может содержать значение 1 (отправить запрос) или 0 (не отправлять запрос). Если proxy = 1, то будет сделан платный запрос (0.01 ₽) на принадлежность IP-адреса сервисам анонимизации (proxy или vpn). Ключ proxy можно не использовать в запросе, если его значение = 0;
- Ключ info может содержать значение 1 (отправить запрос) или 0 (не отправлять запрос). Если info = 1, то будет сделан платный запрос (0.01 ₽) на получение подробной информации о стране, которой принадлежит IP-адрес (столица, площадь и население страны, валюта и код валюты, часовые пояса, домен, телефонный код, граничащие государства, флаг). Ключ info можно не использовать в запросе, если его значение = 0;
- При отправке запроса, в котором одновременно заданы ключи proxy и info стоит учитывать, что ключ proxy должен стоять перед ключем info.

    Используйте в запросе ключ project со значением названия проекта, чтобы статистика запросов отображала количество запросов по Вашему конкретному проекту (если название проекта будет содержать не только латинские буквы, не забудьте делать кодировку при запросе).

###### Защита API-ключа

- Обратите внимание: получить ответ на запрос по конкретному IP-адресу (ключ query) будет невозможно, если в настройках Вашего API-ключа не будут разрешены запросы с любого IP-адреса (*).

###### Пример и описание данных из ответа

    Пример URL на отправку запроса на получение базовой информации и ответ:
    https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ
```json
{
    "as":"AS9009 M247 Ltd",
    "city":"Zurich",
    "country":"Switzerland",
    "countryCode":"CH",
    "isp":"M247 Europe",
    "lat":"47.3769",
    "lon":"8.54169",
    "org":"M247 LTD",
    "query":"37.120.137.58",
    "region":"ZH",
    "regionName":"Zurich",
    "reverse":"",
    "status":"success",
    "timezone":"Europe/Zurich",
    "zip":"8010"
}
```
В данном ответе Вы получаете информацию об IP-адресе, с которого был осуществлен запрос.
При добавлении ключей proxy и/или info будут отправлены дополнительные платные запросы на получение информации об IP-адресе. При желании, укажите в ключе query конкретный IP-адрес.

    Пример URL на отправку запроса на получение максимальной информации:
    https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&proxy=1&info=1

    Пример URL на отправку запроса на получение максимальной информации по конкретному IP-адресу:
    https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=8.8.8.8&proxy=1&info=1

###### Все возможные данные из ответа IP API:

|Название|Описание|Пример|Тип|
| --- | --- | --- | --- |
|as|AS номер (автономная система)|AS9009 M247 Ltd|String|
|city|Город|Zurich|String|
|country|Страна|Switzerland|String|
|countryCode|Двухбуквенный код страны ISO 3166-1 alpha-2|CH|String|
|isp|Интернет-провайдер|M247 Europe|String|
|lat|Latitude (широта)|47.3769|Float|
|lon|Longitude (долгота)|8.54169|Float|
|org|Организация, которой принадлежит IP-адрес|M247 LTD|String|
|query|Запрос|37.120.137.58|String|
|region|Регион / штат / кантон|ZH|String|
|regionName|Полное название региона / штата / кантона|Switzerland|String|
|reverse|Доменные имена в обратной зоне DNS|String|
|status|Статус запроса (fail - отклонен или success - выполнен)|success|String|
|zip|zip / индекс|8010|String|
|proxy|Дополнительный запрос (ключ proxy=1). Ответ yes на принадлежность IP-адреса сервисам анонимизации (proxy или vpn). No - IP-адрес не принадлежит сервисам анонимизации.|yes|String|
|proxyType|Тип прокси / vpn (ipsec, openVPN и другие)|VPN|String|
|proxyProvider|Компания, которая, возможно, предоставляет сервис анонимизации|AS9009 M247 Ltd|String|
|countryInfo|Массив данных по дополнительному запросу по ключу info=1|	
|fullCountryName|Полное название страны|Switzerland|String|
|localizedName|Название страны на главном государственном языке|Schweiz|String|
|topLevelDomain|Интернет-домены страны|.ch [0],[1],[2],[...],[10]|String|
|alpha2Code|Двухбуквенный код страны ISO 3166-1 alpha-2|CH|String|
|alpha3Code|Трехухбуквенный код страны ISO 3166-1 alpha-3|CHE|String|
|numericCode|Цифровой код страны|756|String|
|currencies|Государственная валюта|CHE [0],[1],[2],[...],[10]|String|
|callingCodes|Телефонный код страны|41|String|
|capital|Столица страны|Bern|String|
|flagPng_100px|Ссылка на изображение государственного флага в формате PNG 100x100px. При отправке запроса без HTTPS ссылка на флаг будет подгружаться с домена http://cdn-nossl.ip-api.ru/|https://cdn-ssl.ip-api.ru/flags/png100/ch.png|String|
|flagPng_250px|Ссылка на изображение государственного флага в формате PNG 250x250px. При отправке запроса без HTTPS ссылка на флаг будет подгружаться с домена http://cdn-nossl.ip-api.ru/|https://cdn-ssl.ip-api.ru/flags/png250/ch.png|String|
|flagPng_1000px|Ссылка на изображение государственного флага в формате PNG 1000x1000px. При отправке запроса без HTTPS ссылка на флаг будет подгружаться с домена http://cdn-nossl.ip-api.ru/|https://cdn-ssl.ip-api.ru/flags/png1000/ch.png|String|
|flagSvg|Ссылка на изображение государственного флага в формате SVG. При отправке запроса без HTTPS ссылка на флаг будет подгружаться с домена http://cdn-nossl.ip-api.ru/|https://cdn-ssl.ip-api.ru/flags/svg/ch.svg|String|
|altSpellings|Альтернативные правописания названия страны|Swiss Confederation [0],[1],[2],[...],[10]|String|
|region|Континент|Europe|String|
|subRegion|Принадлежность к группе государств|Western Europe|String|
|language|Государственные языки|German [0],[1],[2],[...],[10]|String|
|languages|Языковые коды ISO 639-1|de [0],[1],[2],[...],[10]|String|
|translations|Название страны на различных мировых языках|Svizzera [0],[1],[2],[...],[10]|String|
|population|Население страны (данные обновляются раз в год)|8256000|Int
|latlon|Широта и долгота|Zurich|47.3769,8.54169
|demonym|Этнохороним (Wiki)|Swiss|String|
|borders|Граничащие государства|AUT [0],[1],[2],[...],[10]|String|
|area|Площадь страны в км2|41284|Int|
|gini|Коэффициент Джини (Wiki)|33.7|Float
|timeZones|Временные зоны страны|UTC+01:00 [0],[1],[2],[...],[10]|String|

###### Использование API
jQuery
```js
$.ajax({
    url: 'https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1',
  	/*HTTP url: 'http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&proxy=0 или 1&info=0 или 1', */    
  	dataType: 'json',
    success: function(data) {
        alert(data.query + '\n' + data.isp + '\n' + data.country + '\n' + data.city);
    }
});
```
Node.js
```js
const request = require('request-promise')
request('https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1')
/* HTTP request('http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1') */

  .then(response => console.log(JSON.parse(response)))
  .catch(err => console.log(err))
```
php
```php
$data = json_decode(file_get_contents('https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1'));
/* HTTP $data = json_decode(file_get_contents('http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1')); */
var_dump($data);
```
Python
```python
requests.get('https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1')
/* HTTP requests.get('http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1') */
```
Ruby
```ruby
require 'json'
require 'open-uri'

JSON.parse(open('https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1').read)
/* HTTP JSON.parse(open('http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1').read) */
```
Kotlin
```kotlin
val result = URL("https://ssl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1").readText()
/* HTTP val result = URL("http://nossl.ip-api.ru/ip-api.json?apiKey=ваш-api-ключ&query=конкретный-IP-адрес&proxy=0 или 1&info=0 или 1").readText() */
```

Официальный сайт сервиса IP-API: https://ip-api.ru/. Документация по всем API: https://ip-api.ru/documentation/ или https://github.com/ip-api-ru/
