# Order

## Get Orders list

```bash
curl "https://api-test.abovegem.com:5443/api/v3/admin/orders?limit=10&offset=0" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-0ba1798c-3018-4a4f-b27b-11b43aea4803' \
  -H 'x-authentication-token: MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNjAxNzI5OTAzNzo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6NzYzdXpTZ0JjNUJGdHB0OHBzV01mRDVCNUxFbGlNSkFlb3Zlb0tla09iVT0'
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

## Get Order details by order id or number

You need put concrete order id to replace :orderIdOrNumber in the url
/v3/admin/orders/:orderIdOrNumber

```bash
curl "https://api-test.abovegem.com:5443/api/v3/admin/orders/1154106" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-request-id: BUU-3rd-wp-c0c285da-4432-4485-8da9-23a52a4e75df' \
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

Response

```json
{
  "id":1154106,
  "orderId":1154106,
  "userId":3271567,
  "distributorId":1433443901,
  "number":"A1154106",
  "state":"complete",
  "email":"dev-test@abovegem.com",
  "countryId":1212,
  "paymentState":"paid",
  "shipmentState":null,
  "specialInstructions":null,
  "orderDate":"2024-01-02T14:03:08.451Z",
  "paymentDate":"2024-01-02T14:03:10.721Z",
  "completedAt":"2024-01-02T14:03:10.721Z",
  "itemTotal":179.99,
  "adjustmentTotal":0,
  "total":179.99,
  "paymentTotal":179.99,
  "creditTotal":0,
  "lineItems":[
    {
      "id":553726,
      "catalogCode":"RW",
      "roleCode":"R",
      "variantId":485,
      "productId":481,
      "productName":"Ellev8 Customer Enrollment",
      "sku":"JOIN-8-CUS-2.0",
      "quantity":1,
      "autoshipQuantity":0,
      "price":179.99,
      "retailPrice":null,
      "amount":179.99,
      "taxAmount":0,
      "amountForTax":179.99,
      "amountAfterDiscount":179.99,
      "imageUrl":"http://buu.abovegem.com:8016//upload/image/1367/580a7366-7543-4ba4-af21-59f56ffb716c.jpg",
      "commissions":[
        {
          "code":"FT",
          "name":"Fast Start Volume",
          "description":"Fast Start Volume",
          "volume":0
        },
        {
          "code":"DT",
          "name":"Dual Team",
          "description":"Dual Team",
          "volume":0
        },
        {
          "code":"QV",
          "name":"Qualification Volume",
          "description":"Qualification Volume",
          "volume":150
        },
        {
          "code":"CV",
          "name":"Commission Volume",
          "description":"Commission Volume",
          "volume":90
        }
      ],
      "personalizedValues":null,
      "canAutoship":false,
      "isPackage":false,
      "taxons":[
        {
          "id":4,
          "taxonomyId":4,
          "parentId":null,
          "position":1,
          "name":"ELLEV8",
          "permalink":"ellev8",
          "lft":null,
          "rgt":null,
          "imageUrl":"678086df-e09a-442b-a89b-fdc80d94e05b.jpg",
          "description":"Ellev8",
          "properties":{

          },
          "displayInShopMenu":true,
          "purchaseRules":null
        },
        {
          "id":10,
          "taxonomyId":10,
          "parentId":null,
          "position":50,
          "name":"Ellev8-PBI",
          "permalink":"ellev8-pbi",
          "lft":null,
          "rgt":null,
          "imageUrl":"",
          "description":"Ellev8 product to be sold in Powered by iGo",
          "properties":{

          },
          "displayInShopMenu":true,
          "purchaseRules":[
            {
              "catalogCode":"RG",
              "roleCode":"D",
              "min":1,
              "max":1
            }
          ]
        }
      ],
      "uVolume":90,
      "qVolume":150,
      "dtVolume":0,
      "additional":{

      },
      "options":{

      },
      "images":[
        "http://buu.abovegem.com:8016//upload/image/1367/580a7366-7543-4ba4-af21-59f56ffb716c.jpg"
      ],
      "actualCv":90,
      "actualQv":150
    }
  ],
  "adjustments":[

  ],
  "billingAddress":{
    "id":17617251,
    "firstName":"Ishan",
    "m":"",
    "lastName":"Sharma",
    "phone":"8888888888",
    "email":"dev-test@abovegem.com",
    "street":"Twar 9, Sahari Village, Ras al Khor",
    "streetCont":null,
    "city":"Dubai",
    "zip":"0000",
    "state":"دبي",
    "stateId":12159,
    "country":"United Arab Emirates",
    "countryId":1212,
    "countryCode":"971",
    "personalPrefixId":null,
    "personalPrefixName":null,
    "personalSuffixId":null,
    "personalSuffixName":null
  },
  "shippingAddress":{
    "id":17617250,
    "firstName":"Ishan",
    "m":"",
    "lastName":"Sharma",
    "phone":"8888888888",
    "email":"dev-test@abovegem.com",
    "street":"Twar 9, Sahari Village, Ras al Khor",
    "streetCont":null,
    "city":"Dubai",
    "zip":"0000",
    "state":"دبي",
    "stateId":12159,
    "country":"United Arab Emirates",
    "countryId":1212,
    "countryCode":"971",
    "personalPrefixId":null,
    "personalPrefixName":null,
    "personalSuffixId":null,
    "personalSuffixName":null
  },
  "shippingMethodId":null,
  "shippingMethod":null,
  "shippingTrackingNumber":"",
  "shippingTrackingInfos":[

  ],
  "availableShippingMethods":[

  ],
  "availablePaymentMethods":[
    {
      "id":3,
      "name":"Credit Card",
      "description":"<p><br></p>",
      "cardTypes":[
        "mastercard",
        "visa"
      ],
      "gatewayParameters":null,
      "isDefault":true,
      "isCreditcard":true,
      "isWallet":false,
      "isWireTransfer":false,
      "isGiftCard":false,
      "isDebitcard":false,
      "isDebitRedirect":false,
      "isCash":false,
      "isPush":false,
      "isRedemption":false,
      "isMyEWallet":false,
      "isFreePay":false,
      "isRedirect":false,
      "isPayPal":false,
      "isSquare":false,
      "isPeach":false
    },
    {
      "id":9,
      "name":"iGoPay",
      "description":"<p>Charge will appear as \"Powered by iGo\" on your Card or Bank Statement</p>",
      "cardTypes":[
        "mastercard",
        "visa"
      ],
      "gatewayParameters":null,
      "isDefault":false,
      "isCreditcard":true,
      "isWallet":false,
      "isWireTransfer":false,
      "isGiftCard":false,
      "isDebitcard":false,
      "isDebitRedirect":false,
      "isCash":false,
      "isPush":false,
      "isRedemption":false,
      "isMyEWallet":false,
      "isFreePay":false,
      "isRedirect":false,
      "isPayPal":false,
      "isSquare":false,
      "isPeach":false
    }
  ],
  "availableCoupons":[

  ],
  "coupons":[

  ],
  "commissions":[
    {
      "name":"BV",
      "value":150
    }
  ],
  "payments":[
    {
      "id":397974,
      "amount":179.99,
      "paymentMethodId":9,
      "paymentMethodName":"iGoPay",
      "paymentMethodType":"CreditCard",
      "hasPaymentDetail":true,
      "paymentUserName":"Ishan Sharma",
      "canCapture":false,
      "translationId":"9071832983",
      "type":"Creditcard",
      "state":"completed",
      "createdAt":"2024-01-02T14:03:08.686Z",
      "updatedAt":"2024-01-02T14:03:10.716Z",
      "last4Digits":"5173",
      "billingAddress":{
        "id":17617251,
        "firstName":"Ishan",
        "m":"",
        "lastName":"Sharma",
        "phone":"8888888888",
        "email":null,
        "street":"Twar 9, Sahari Village, Ras al Khor",
        "streetCont":null,
        "city":"Dubai",
        "zip":"0000",
        "state":"دبي",
        "stateId":12159,
        "country":"United Arab Emirates",
        "countryId":1212,
        "countryCode":"971",
        "personalPrefixId":null,
        "personalPrefixName":null,
        "personalSuffixId":null,
        "personalSuffixName":null
      }
    }
  ],
  "orderType":{
    "id":5,
    "name":"Renewal",
    "code":"RW",
    "description":null
  },
  "currency":{
    "isoCode":"USD",
    "symbol":"$",
    "numDecimals":2
  },
  "country":{
    "id":1212,
    "name":"United Arab Emirates",
    "iso":"AE"
  },
  "shipments":[

  ],
  "userInfo":{
    "email":"dev-test@abovegem.com",
    "name":"Ishan Sharma",
    "distributorId":1433443901,
    "roleCode":"R",
    "roleName":"Retail Customer",
    "countryId":1212,
    "countryName":"United Arab Emirates"
  },
  "sponsorInfo":{
    "userId":2302219,
    "distributorId":1009306101,
    "email":"dev-test@abovegem.com",
    "name":"David Sayers",
    "phone":"8888888888"
  },
  "canPayAgain":false,
  "autoshipType":"tokenization",
  "legalEntities":[
    {
      "name":"ibuumerang",
      "address":{
        "id":17324276,
        "firstName":null,
        "m":null,
        "lastName":null,
        "phone":"8888888888",
        "email":"dev-test@abovegem.com",
        "street":"11391 Meadowglen Lane",
        "streetCont":"Suite A1",
        "city":"Houston",
        "zip":"77082",
        "state":"Texas",
        "stateId":10057,
        "country":"United States",
        "countryId":1214,
        "countryCode":"1",
        "personalPrefixId":null,
        "personalPrefixName":null,
        "personalSuffixId":null,
        "personalSuffixName":null
      }
    }
  ],
  "adminNotes":[

  ],
  "isOrderCanRefund":false,
  "returnAmountInfo":{
    "received":0,
    "refunded":0
  },
  "error":null,
  "isGiftCardOrder":false
}
```
