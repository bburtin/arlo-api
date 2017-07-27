# Netgear Arlo REST API documentation

## Authentication

POST to https://arlo.netgear.com/hmsweb/login/v2

Request payload:
```
{
    "email": "test@example.com",
    "password": "secret"
}
```
Response payload:
```
{
    "data": {
        "accountStatus": "registered",
        "arlo": true,
        "authenticated": 12345,
        "countryCode": "US",
        "dateCreated": 1499819317539,
        "email": "test@example.com",
        "paymentId": "12345",
        "policyUpdate": false,
        "serialNumber": "ABCDE",
        "tocUpdate": false,
        "token": "2_59q2OAuX1d0nu-Z6Z1rq5gbInuS6iUVoZ...",
        "userId": "MQ123-456-12345678",
        "validEmail": true
    },
    "success": true
}
```
