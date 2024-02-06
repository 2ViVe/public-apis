# Commission

## Get weekly / monthly commission dates

```bash
curl "https://api-test.abovegem.com:5443/api/v2/admin/commissions/dates?periods=monthly" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-487009cc-bd7b-4a3b-88c7-53cfc0b3d224' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param   | type   | value            | required | comment                       |
| ------- | ------ | ---------------- | -------- | ----------------------------- |
| periods | string | weekly / monthly | Required | get commission date by period |

Response

```json
{
  "monthly":{
    "2023":[
      "1201",
      "1101",
      "1001",
      "0901",
      "0801",
      "0701",
      "0601",
      "0501",
      "0401",
      "0301",
      "0201",
      "0101"
    ],
    "2024":[
      "0101"
    ]
  }
}
```

## Get Weekly / Monthly commission report

```bash
curl "https://api-test.abovegem.com:5443/api/v2/admin/commissions/monthly2?date=20240115&period=weekly&limit=10&offset=0" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-971e7201-8652-4ab6-8de3-593300aa99d4' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param   | type    | value               | required | comment                                                                                                         |
| ------- | ------- | ------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| limit   | integer | 1~100               | Required | used for pagenation. donot try to fetch hudge orders!                                                           |
| offset  | integer | 0~n                 | Required | used for pagenation offset                                                                                      |
| periods | string  | weekly / monthly    | Required | get weekly / montly commission date. should append with the right date period from the get commission dates api |
| date    | string  | 20240115 / 20240101 | Required | the commission period start date                                                                                |

Response

```json
{
  "names":[
    "Distributor ID",
    "TSA Number",
    "Distributor Name",
    "Tax Number",
    "Country",
    "Date Of Birth",
    "Email",
    "Enrollment Date",
    "Status",
    "Retail",
    "Dual Team",
    "Fast Start",
    "Total"
  ],
  "values":[
    [
      1005776001,
      "TSA2685908",
      "RENEE HICKS",
      "",
      "US",
      "1957-01-17",
      "dev-test@abovegem.com",
      "2019-03-02",
      "In-service",
      29.99,
      0,
      0,
      29.99
    ],
    [
      1007103301,
      "TSA5488095",
      "Cierra Benton",
      "",
      "US",
      "1987-07-02",
      "dev-test@abovegem.com",
      "2020-10-09",
      "In-service",
      49.99,
      0,
      0,
      49.99
    ]
  ]
}
```

## Get Weekly / Monthly commission summary

```bash
curl "https://api-test.abovegem.com:5443/api/v2/admin/commissions/summaries?date=20240115&period=weekly" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-9ab009b8-0707-491a-8b7d-cf5b29a34681' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param     | type    | value               | required | comment                                                                                                         |
| --------- | ------- | ------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| periods   | string  | weekly / monthly    | Required | get weekly / montly commission date. should append with the right date period from the get commission dates api |
| date      | string  | 20240115 / 20240101 | Required | the commission period start date                                                                                |
| countryId | integer | 1214                | Optional | search by country                                                                                               |

Response

```json
[
  {
    "name":"Dual Team",
    "code":"DTM",
    "period":"weekly",
    "total":30150.6,
    "count":1165820
  },
  {
    "name":"Fast Start",
    "code":"FSB",
    "period":"weekly",
    "total":7534.2,
    "count":73
  },
  {
    "name":"Retail",
    "code":"RC",
    "period":"weekly",
    "total":4107.68,
    "count":85
  }
]
```

```json
[
  {
    "name":"Unilevel",
    "code":"UC",
    "period":"monthly",
    "total":68134.46,
    "count":283
  },
  {
    "name":"Generation",
    "code":"GEN",
    "period":"monthly",
    "total":10076.54,
    "count":8
  },
  {
    "name":"Lifestyle",
    "code":"LFE",
    "period":"monthly",
    "total":8500,
    "count":17
  },
  {
    "name":"Star Achiever",
    "code":"SAR",
    "period":"monthly",
    "total":3828,
    "count":19
  }
]
```

## Get commission summary users

the :id 1008449301 should be concrete rep id.

```bash
curl "https://api-test.abovegem.com:5443/api/v2/admin/commissions/summaries/users/1008449301?date=20240101&period=monthly" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-07eb3293-54f2-4418-ac17-fef623e1b804' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param   | type   | value               | required | comment                                                                                                         |
| ------- | ------ | ------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| periods | string | weekly / monthly    | Required | get weekly / montly commission date. should append with the right date period from the get commission dates api |
| date    | string | 20240115 / 20240101 | Required | the commission period start date                                                                                |

Response

```json
[
  {
    "name":"Unilevel",
    "code":"UC",
    "period":"monthly",
    "total":13463.11
  },
  {
    "name":"Generation",
    "code":"GEN",
    "period":"monthly",
    "total":4650.49
  },
  {
    "name":"Lifestyle",
    "code":"LFE",
    "period":"monthly",
    "total":1000
  }
]
```

## Get all data summary

```bash
curl "https://api-test.abovegem.com:5443/api/v3/admin/reports/genealogy/unilevel/order-summary?limit=100&offset=0&startDate=2024-01-01T00%3A00%3A00-06%3A00&endDate=2024-01-31T23%3A59%3A59-06%3A00&distributorId=1005776001&flag=&orderOnly=false" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-e072c92d-8393-4653-9f77-aaa173dd37c5' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param         | type               | value                           | required | comment                                               |
| ------------- | ------------------ | ------------------------------- | -------- | ----------------------------------------------------- |
| limit         | integer            | 1~100                           | Required | used for pagenation. donot try to fetch hudge orders! |
| offset        | integer            | 0~n                             | Required | used for pagenation offset                            |
| startDate     | url encoded string | 2024-01-01T00%3A00%3A00-06%3A00 | Required | start date                                            |
| endDate       | url encoded string | 2024-01-31T23%3A59%3A59-06%3A00 | Required | end date                                              |
| distributorId | integer            | 1005776001                      | Required | concrete distributor id                               |
| flag          | string             | "" / personal / front-line      | Required | search by genealogy view type                         |
| orderOnly     | boolean            | true / false                    | Optional | search with order only                                |

Response

```json
[
  {
    "level":0,
    "email":"dev-test@abovegem.com",
    "distributorId":1005776001,
    "distributorName":"RENEE HICKS",
    "ulSponsorId":1007749101,
    "ulSponsorName":"Mardi Maione",
    "entryDate":"2019-03-02T08:00:00.000Z",
    "roleStartDate":"2019-03-02T08:00:00.000Z",
    "roleCode":"D",
    "countryName":"United States",
    "orderTotal":579.93,
    "pqvTotal":550,
    "orderCount":3
  }
]
```

## Get all data orders

```bash
curl -x 127.0.0.1:8888 -k "https://api-test.abovegem.com:5443/api/v3/admin/reports/genealogy/unilevel/orders?limit=-1&offset=0&startDate=2024-01-01T00%3A00%3A00-06%3A00&endDate=2024-01-31T23%3A59%3A59-06%3A00&distributorId=1005776001&sponsorId=1007749101&flag=personal" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-e072c92d-8393-4653-9f77-aaa173dd37c5' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNzIxOTM4MDIxMTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6Z1FoNjRGcEhzVFExcmh2djJuSjM5Wi94K3oyL1VsVllhQ3FlczJ2WjBxMD0='
```

Headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param         | type               | value                           | required | comment                                               |
| ------------- | ------------------ | ------------------------------- | -------- | ----------------------------------------------------- |
| limit         | integer            | 1~100                           | Required | used for pagenation. donot try to fetch hudge orders! |
| offset        | integer            | 0~n                             | Required | used for pagenation offset                            |
| startDate     | url encoded string | 2024-01-01T00%3A00%3A00-06%3A00 | Required | start date                                            |
| endDate       | url encoded string | 2024-01-31T23%3A59%3A59-06%3A00 | Required | end date                                              |
| distributorId | integer            | 1005776001                      | Required | concrete distributor id                               |
| sponsorId     | integer            | 1007749101                      | Required | sponsor id                                            |
| flag          | string             | "" / personal / front-line      | Required | search by genealogy view type                         |

Response

```json
[
  {
    "level":0,
    "orderId":1157135,
    "orderNumber":"A1157135",
    "orderTotal":99.95,
    "orderState":"complete",
    "commissionDate":"2024-01-17T11:03:06.300Z",
    "roleCode":"D",
    "distributorId":1005776001,
    "distributorName":"RENEE HICKS",
    "ulSponsorId":1007749101,
    "ulSponsorName":"Mardi Maione",
    "orderDistributorId":1005776001,
    "orderUserName":"RENEE HICKS",
    "pvq":100,
    "isFirstOrder":false
  },
  {
    "level":0,
    "orderId":1156942,
    "orderNumber":"A1156942",
    "orderTotal":179.99,
    "orderState":"complete",
    "commissionDate":"2024-01-16T13:03:03.953Z",
    "roleCode":"R",
    "distributorId":1005776001,
    "distributorName":"RENEE HICKS",
    "ulSponsorId":1007749101,
    "ulSponsorName":"Mardi Maione",
    "orderDistributorId":1069192801,
    "orderUserName":"renee hicks",
    "pvq":150,
    "isFirstOrder":false
  },
  {
    "level":0,
    "orderId":1156821,
    "orderNumber":"N1156821",
    "orderTotal":299.99,
    "orderState":"complete",
    "commissionDate":"2024-01-16T00:33:25.276Z",
    "roleCode":"D",
    "distributorId":1005776001,
    "distributorName":"RENEE HICKS",
    "ulSponsorId":1007749101,
    "ulSponsorName":"Mardi Maione",
    "orderDistributorId":1005776001,
    "orderUserName":"RENEE HICKS",
    "pvq":300,
    "isFirstOrder":false
  }
]
```
