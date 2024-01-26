# User

## Get Users list

```bash
curl "https://api-test.abovegem.com:5443/api/v3/admin/users?limit=10&offset=0" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-1861bfcc-a48c-4e47-a216-e3d9921a2e2c' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNjI3NjQyMjAyOTo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6REdvekJuNXdPUU9MSTRQTmt0K1JEaUIxdXc4UGREZVJzblovSGh0ejdYaz0'
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

| param         | type               | value               | required | comment                                               |
| ------------- | ------------------ | ------------------- | -------- | ----------------------------------------------------- |
| limit         | integer            | 1~100               | Required | used for pagenation. donot try to fetch hudge orders! |
| offset        | integer            | 0~n                 | Required | used for pagenation offset                            |
| distributorId | integer            | 1451957701          | Optional | search by distributor id                              |
| login         | string             | usd01262            | Optional | search by users login                                 |
| sponsorId     | integer            | 1007799401          | Optional | search by sponsor id                                  |
| email         | url encoded string | usd01262%40test.com | Optional | search by users email                                 |
| statusCode    | integer            | 1                   | Optional | search by user status code                            |
| rankCode      | integer            | 0                   | Optional | search by lifetime rank code                          |

User status code defintion

| code | status       |
| ---- | ------------ |
| 1    | in-service   |
| 2    | unregistered |
| 3    | cancelled    |
| 4    | inactive     |
| 5    | revoked      |
| 6    | terminated   |
| 7    | suspended    |

Lifetime Rank defintion

| rank_identity | name                |
| ------------- | ------------------- |
| 0             | init                |
| 10            | New Member          |
| 20            | Retail Customer     |
| 30            | Preferred Customer  |
| 40            | Ambassador          |
| 45            | Affiliate           |
| 50            | Coach               |
| 55            | Executive           |
| 60            | Business            |
| 65            | CEO                 |
| 70            | FirstClass          |
| 80            | Director            |
| 90            | SeniorDirector      |
| 100           | ExecutiveDirector   |
| 110           | Sapphire            |
| 120           | Ruby                |
| 130           | Emerald             |
| 140           | Diamond             |
| 150           | BlueDiamond         |
| 160           | BlackDiamond        |
| 170           | PresidentialDiamond |
| 180           | CrownDiamond        |
| 190           | DoubleCrownDiamond  |
| 200           | TripleCrownDiamond  |

Response

```json
{
  "users":[
    {
      "channel":null,
      "taxnumber":null,
      "company":null,
      "username":"usd01262",
      "email":"usd01262@test.com",
      "name":"usd01262 usr",
      "address1":"x x",
      "address2":"",
      "city":"los angeles",
      "zipcode":"90007",
      "phone":"4085477436",
      "iso":"US",
      "services":null,
      "imageUrl":"http://buu.abovegem.com:8016//upload/default_avatar/618/a015d910-2476-11ec-b944-f7f813fa948c.png",
      "distributorId":1451957701,
      "userId":3290081,
      "nextRenewalDate":"2024-02-26T01:00:00.000Z",
      "serviceRenewalDate":"2024-02-26T02:07:31.820Z",
      "dateOfBirth":"1980-01-01",
      "dualteamSponsorId":1451956901,
      "dualteamPosition":"L",
      "matrixSponsorId":null,
      "matrixPosition":null,
      "sponsorId":1007799401,
      "externalDistributorId":"TSA1451957701",
      "channelOthers":null,
      "taxnumberExemption":null,
      "socialSecurityNumber":null,
      "entryDate":"2024-01-26T01:58:15.033Z",
      "roleStartDate":"2024-01-26T01:58:15.033Z",
      "entryOperator":null,
      "statusName":"In-service",
      "statusCode":"A",
      "roleName":"Distributor",
      "roleCode":"D",
      "lifetimeRankName":"Ambassador",
      "jointFirstname":"",
      "jointLastname":"",
      "countryCode":"1",
      "countryName":"United States",
      "countryId":1214,
      "stateId":10018,
      "stateName":"California",
      "preferredLanguageId":null,
      "assetId":618,
      "attachmentFileName":"a015d910-2476-11ec-b944-f7f813fa948c.png",
      "assetType":"Default_Avatar",
      "presonalPrefixName":null,
      "sponsorName":"Elite Marketing",
      "dualteamSponsorName":"usd01261 usr",
      "enrollerId":1007799401,
      "enrollerName":"Elite Marketing",
      "entryOperatorName":null,
      "referralInfo":null,
      "isGuestUser":false,
      "orderCount":0
    }
  ]
}

```
