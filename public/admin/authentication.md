# Authentication

## Post Authentication Token

```bash
curl "http://api-demo.abovegem.com:11442/api/v3/admin/authentications/token" \
  -H 'content-type: application/json' \
  -H 'x-company-code: BUU' \
  -H 'x-client-id: test_client_id_buu_1' \
  -H 'x-client-secret: test_client_secret_buu_1' \
  -H 'x-device-uuid: some-test-device-uuid-here' \
  -H 'x-device-info: wordpress' \
  -H 'x-request-id: BUU-3rd-wp-7f79e3f5-c2f4-4a73-92c5-66e78511ee60' \
  -d '{"user": "testapiadmin", "password":"Abc123456"}' 
```

HTTP Headers

| header          | value                    | required | comment                               |
| --------------- | ------------------------ | -------- | ------------------------------------- |
| content-type    | application/json         | Required | define api communicate as json syntax |
| x-company-code  | BUU                      | Required | api company code                      |
| x-client-id     | test_client_id_buu_1     | Required | client id for authentication          |
| x-client-secret | test_client_secret_buu_1 | Required | client secret for authentication      |
| x-device-uuid   | some uuid generated      | Optional | device uuid for debug                 |
| x-device-info   | some device info         | Optional | device info for debug                 |
| x-request-id    | some unique request id   | Optional | request id for log trace              |

Body

| field    | value        | required | comment      |
| -------- | ------------ | -------- | ------------ |
| user     | testapiadmin | Required | the login    |
| password | Abc123456    | Required | the password |

Response

```json
{
  "authenticationToken":"MTQ1MTk0MzYwMTo6MzI5MDA2Nzo6dGVzdGFwaWFkbWluOjpzb21lLXRlc3QtZGV2aWNlLXV1aWQtaGVyZTo6MTcwNjAxNzI5OTAzNzo6dGVzdF9jbGllbnRfaWRfYnV1XzE6OkJVVTo6TTo6NzYzdXpTZ0JjNUJGdHB0OHBzV01mRDVCNUxFbGlNSkFlb3Zlb0tla09iVT0="
}
```
