# Order

## Get Orders

```bash
curl -x 127.0.0.1:8888 -k "http://api-demo.abovegem.com:11442/api/v3/admin/orders?limit=10&offset=0" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-0ba1798c-3018-4a4f-b27b-11b43aea4803' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNjAxNzI5OTAzNzo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6NzYzdXpTZ0JjNUJGdHB0OHBzV01mRDVCNUxFbGlNSkFlb3Zlb0tla09iVT0'
```

Params

| param             | value                           | required | comment                                                                                      |
| ----------------- | ------------------------------- | -------- | -------------------------------------------------------------------------------------------- |
| limit             | 1~100                           | Required | used for pagenation. donot try to fetch hudge orders!                                        |
| offset            | 0~n                             | Required | used for pagenation offset                                                                   |
| sku               | BASIC_KIT                       | Optional | search specfield product orders via single sku                                               |
| sponsorId         | 1435250601                      | Optional | search concrete sponsors orders. cannot search with external distributor id (TSA number etc) |
| productName       | BUSINESS+KIT                    | Optional | search specfield product orders via single product name                                      |
| orderDateStart    | 2024-01-01T00%3A00%3A00-06%3A00 | Optional | query orders by date range                                                                   |
| orderDateEnd      | 2024-01-02T23%3A59%3A59-06%3A00 | Optional | query orders by date range                                                                   |
| transactionNumber | 9071832983                      | Optional | search order by payment transaction ID                                                       |

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
