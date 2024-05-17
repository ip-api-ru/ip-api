# IP API: максимальная информация об IP-адресе (Geolocation)

###### Версия API

- 4.0 (от 15 мая 2024 года).

###### HTTPS

- Поддержка HTTPS осуществляется только через адрес https://prod.ip-api.ru/;

###### Ключи

- Обязательным ключем является token - Ваш уникальный API-токен для доступа к сервису;
- Ключ query может содержать IP-адрес (ipv4/ipv6) или домен. Ключ query можно не использовать в запросе, если требуется информация об IP-адресе, с которого был сделан запрос;

Полный пример URL с token и query: https://prod.ip-api.ru/checkIP/1.1.1.1?token=abcd

###### Демо-доступ
Без ключа token доступ к API ограничен одним запросом в 10 скуенд.

###### Пример и описание данных из ответа

    Пример URL на отправку запроса на получение полной информации и ответ:
    https://prod.ip-api.ru/checkIP/79.168.170.21?token=abcd
```json
{
   "status":"ok",
   "72.161.70.21":{
      "asn":"AS22561",
      "range":"72.161.70.0/22",
      "hostName":"72-161-70-21.dyn.centurytel.net",
      "provider":"CenturyLink Communications, LLC",
      "org":"CenturyLink Communications, LLC",
      "anonymity":{
         "proxy":"no",
         "type":"Business"
      },
      "risk":{
         "value":"unknown"
      },
      "location":{
         "continent":"North America",
         "continentCode":"NA",
         "country":"United States",
         "isoCode":"US",
         "region":"New York",
         "regionCode":"NY",
         "timezone":"America/New_York",
         "city":"New York",
         "postCode":"10123",
         "lat":"40.7128",
         "lon":"-74.006",
         "currency":{
            "code":"USD",
            "name":"Dollar",
            "symbol":"$"
         },
         "assets":{
            "flags":{
               "waving":{
                  "0":"https://prod.ip-api.ru/assets/flags/16x12/US.png",
                  "1":"https://prod.ip-api.ru/assets/flags/20x15/US.png",
                  "2":"https://prod.ip-api.ru/assets/flags/24x18/US.png",
                  "3":"https://prod.ip-api.ru/assets/flags/28x21/US.png",
                  "4":"https://prod.ip-api.ru/assets/flags/32x24/US.png",
                  "5":"https://prod.ip-api.ru/assets/flags/36x27/US.png",
                  "6":"https://prod.ip-api.ru/assets/flags/40x30/US.png",
                  "7":"https://prod.ip-api.ru/assets/flags/48x36/US.png",
                  "8":"https://prod.ip-api.ru/assets/flags/56x42/US.png",
                  "9":"https://prod.ip-api.ru/assets/flags/60x45/US.png",
                  "10":"https://prod.ip-api.ru/assets/flags/64x48/US.png",
                  "11":"https://prod.ip-api.ru/assets/flags/72x54/US.png",
                  "12":"https://prod.ip-api.ru/assets/flags/80x60/US.png",
                  "13":"https://prod.ip-api.ru/assets/flags/84x63/US.png",
                  "14":"https://prod.ip-api.ru/assets/flags/96x72/US.png",
                  "15":"https://prod.ip-api.ru/assets/flags/108x81/US.png",
                  "16":"https://prod.ip-api.ru/assets/flags/112x84/US.png",
                  "17":"https://prod.ip-api.ru/assets/flags/120x90/US.png",
                  "18":"https://prod.ip-api.ru/assets/flags/128x96/US.png",
                  "19":"https://prod.ip-api.ru/assets/flags/144x108/US.png",
                  "20":"https://prod.ip-api.ru/assets/flags/160x120/US.png",
                  "21":"https://prod.ip-api.ru/assets/flags/192x144/US.png",
                  "22":"https://prod.ip-api.ru/assets/flags/224x168/US.png",
                  "23":"https://prod.ip-api.ru/assets/flags/256x192/US.png"
               },
               "original":{
                  "sameWidth":{
                     "0":"https://prod.ip-api.ru/assets/flags/w20/US.png",
                     "1":"https://prod.ip-api.ru/assets/flags/w40/US.png",
                     "2":"https://prod.ip-api.ru/assets/flags/w80/US.png",
                     "3":"https://prod.ip-api.ru/assets/flags/w160/US.png",
                     "4":"https://prod.ip-api.ru/assets/flags/w320/US.png",
                     "5":"https://prod.ip-api.ru/assets/flags/w640/US.png",
                     "6":"https://prod.ip-api.ru/assets/flags/w1280/US.png",
                     "7":"https://prod.ip-api.ru/assets/flags/w2560/US.png"
                  },
                  "sameHeight":{
                     "0":"https://prod.ip-api.ru/assets/flags/h20/US.png",
                     "1":"https://prod.ip-api.ru/assets/flags/h24/US.png",
                     "2":"https://prod.ip-api.ru/assets/flags/h40/US.png",
                     "3":"https://prod.ip-api.ru/assets/flags/h60/US.png",
                     "4":"https://prod.ip-api.ru/assets/flags/h80/US.png",
                     "5":"https://prod.ip-api.ru/assets/flags/h120/US.png",
                     "6":"https://prod.ip-api.ru/assets/flags/h240/US.png"
                  }
               }
            }
         }
      },
      "userConnectionInfo":{
         "userAgent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:125.0) Gecko/20100101 Firefox/125.0"
      }
   },
   "imprint":{
      "endpointUrl":"https://prod.ip-api.ru/checkIP/imprint/",
      "X-IMPRINT":"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",
      "description_ru":"С результата этого запроса был сделан отпечаток. Посмотреть полное содержание в любое время можно через отправку запроса на endpointUrl с содержанием заголовка X-IMPRINT."
   }
}
```


Официальный сайт сервиса IP-API: https://ip-api.ru/ *** https://github.com/ip-api-ru/
