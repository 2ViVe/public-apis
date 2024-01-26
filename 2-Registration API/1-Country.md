# Country

## GET countries

```bash
curl "https://api-test.abovegem.com:5443/api/v3/registrations/countries" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-client-secret: test_client_secret_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-6b689628-130f-4c1d-882e-9a5f40f39262'
```

HTTP Headers

| header          | value                    | required | comment                               |
| --------------- | ------------------------ | -------- | ------------------------------------- |
| content-type    | application/json         | Required | define api communicate as json syntax |
| x-company-code  | BUU                      | Required | api company code                      |
| x-client-id     | test_client_id_buu_1     | Required | client id for authentication          |
| x-client-secret | test_client_secret_buu_1 | Required | client secret for authentication      |
| x-request-id    | some unique request id   | Optional | request id for log trace              |

Response

```json
[
  {
    "id":1221,
    "name":"Virgin Islands, U.S.",
    "iso":"VI",
    "iso3":"VIR",
    "currency":{
      "id":149,
      "symbol":"$",
      "isoCode":"USD",
      "numDecimals":2
    },
    "states":[
      {
        "id":13066,
        "name":"Virgin Islands, U.S.",
        "abbr":"Virgin Islands, U.S.",
        "countryId":1221
      }
    ],
    "currencyId":149,
    "continentId":6,
    "timezoneId":null,
    "continentName":"North America",
    "countryCode":"1-340"
  }
]
```


