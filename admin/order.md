# Order

## Get Orders

```bash
curl "https://api-test.abovegem.com:5443/api/v3/admin/orders?limit=10&offset=0" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-0ba1798c-3018-4a4f-b27b-11b43aea4803' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNjAxNzI5OTAzNzo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6NzYzdXpTZ0JjNUJGdHB0OHBzV01mRDVCNUxFbGlNSkFlb3Zlb0tla09iVT0'
```

headers

| header                 | value                   | required | comment                               |
| ---------------------- | ----------------------- | -------- | ------------------------------------- |
| content-type           | application/json        | Required | define api communicate as json syntax |
| x-company-code         | BUU                     | Required | api company code                      |
| x-client-id            | test_client_id_buu_1    | Required | client id from authentication         |
| x-request-id           | some unique request id  | Optional | request id for log trace              |
| x-authentication-token | the base64 token string | Required | the authorized token                  |

Params

| param             | type               | value                                                       | required | comment                                                                                      |
| ----------------- | ------------------ | ----------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------- |
| limit             | integer            | 1~100                                                       | Required | used for pagenation. donot try to fetch hudge orders!                                        |
| offset            | integer            | 0~n                                                         | Required | used for pagenation offset                                                                   |
| sku               | string             | BASIC_KIT                                                   | Optional | search specfield product orders via single sku                                               |
| sponsorId         | integer            | 1435250601                                                  | Optional | search concrete sponsors orders. cannot search with external distributor id (TSA number etc) |
| productName       | url encoded string | BUSINESS+KIT                                                | Optional | search specfield product orders via single product name                                      |
| orderDateStart    | url encoded string | 2024-01-01T00%3A00%3A00-06%3A00                             | Optional | query orders by date range                                                                   |
| orderDateEnd      | url encoded string | 2024-01-02T23%3A59%3A59-06%3A00                             | Optional | query orders by date range                                                                   |
| transactionNumber | string             | 9071832983                                                  | Optional | search order by payment transaction ID                                                       |
| firstName         | string             | Ishan                                                       | Optional | search order first name                                                                      |
| lastName          | string             | Sharma                                                      | Optional | search order last name                                                                       |
| shiptoFirstName   | string             | Ishan                                                       | Optional | search order shipto first name                                                               |
| shiptoLastName    | string             | Sharma                                                      | Optional | search order shipto last name                                                                |
| shipmentState     | string             | ready / assemble / shipped                                  | Optional | search order by shipment state                                                               |
| orderType         | String             | CM / RG / RW                                                | Optional | search order by order type Shopping, Registration, Renewal                                   |
| orderState        | String             | complete / cancelled / returned / payment / awaiting_return | Optional | search order by order state                                                                  |
| paymentState      | String             | paid / balance_due / credit_owed / refund                   | Optional | search order by payment state                                                                |
| roleCode          | String             | D / R                                                       | Optional | search order by role Distributor / Customer                                                  |
| countryId         | integer            | 1214                                                        | Optional | search order by country id. country id can fetch by countries api                            |

Responses

```json
{
  "orders":[
    {
      "state":"complete",
      "total":179.99,
      "email":"dev-test@abovegem.com",
      "source":"web",
      "pvq":150,
      "ips":[
        "::1"
      ],
      "hasnote":false,
      "country":{
        "id":1212,
        "name":"United Arab Emirates",
        "stateName":"دبي",
        "iso":"AE"
      },
      "currency":{
        "isoCode":"USD",
        "symbol":"$",
        "numDecimals":2
      },
      "orderId":1154106,
      "orderNumber":"A1154106",
      "userId":3271567,
      "orderDate":"2024-01-02T14:03:08.451Z",
      "completedAt":"2024-01-02T14:03:10.721Z",
      "paymentDate":"2024-01-02T14:03:10.721Z",
      "commissionDate":"2024-01-02T14:03:10.721Z",
      "paymentState":"paid",
      "shipmentState":null,
      "creditTotal":0,
      "shippingMethodId":null,
      "isAutoship":true,
      "specialInstructions":null,
      "isGuest":true,
      "distributorId":1433443901,
      "distributorName":"Ishan Sharma",
      "sponsorId":1009306101,
      "shippingMethodName":null,
      "roleName":"Retail Customer",
      "roleCode":"R",
      "orderTypeName":"Renewal",
      "orderTypeCode":"RW",
      "shippingAddress":{
        "id":17617250,
        "firstname":"Ishan",
        "middleabbr":"",
        "lastname":"Sharma",
        "address1":"Twar 9, Sahari Village, Ras al Khor",
        "address2":null,
        "city":"Dubai",
        "zipcode":"0000",
        "phone":"8888888888",
        "fax":null,
        "email":null,
        "county":null,
        "name":"Ishan Sharma",
        "stateId":12159,
        "countryId":1212,
        "stateName":"دبي",
        "alternativePhone":null,
        "mobilePhone":"8888888888",
        "jointFirstname":null,
        "jointMiddleabbr":null,
        "jointLastname":null,
        "createdAt":"2022-12-02T14:44:49.249+00:00",
        "updatedAt":"2022-12-02T14:44:49.249+00:00",
        "personalTitleId":null,
        "personalPrefixId":null,
        "personalSuffixId":null,
        "countryName":"United Arab Emirates",
        "countryIso":"AE"
      },
      "homeAddress":{
        "name":"Ishan Sharma",
        "countryName":"United Arab Emirates",
        "stateName":"دبي",
        "countryIso":"AE",
        "countryId":1212
      },
      "sponsorName":"David Sayers",
      "entryOperatorName":" ",
      "paymentMethods":[
        {
          "name":"iGoPay",
          "state":"completed",
          "responseCode":"9071832983"
        }
      ],
      "pvDt":0,
      "pvUl":90,
      "fastTrack":0,
      "isAdmin":true,
      "partyId":null,
      "partyHost":null,
      "isOrderCanRefund":false,
      "isFirstOrder":false
    }
  ]
}
```
