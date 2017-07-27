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

For subsequent requests, set the `Authorization` header to the `token` returned in the login response.

## Service level

GET https://arlo.netgear.com/hmsweb/users/serviceLevel

Response payload:
```
{
    "data": [
        {
            "billingDate": null,
            "createdDate": 1499819320594,
            "cvrAccessExpiry": 7,
            "daysLeftForExpiry": null,
            "display": "FREE",
            "expiryDate": null,
            "groupName": "Basic",
            "groupNumber": 0,
            "isBusiness": null,
            "lastModified": 1499819320594,
            "libraryAccessExpiry": 7,
            "maxAccounts": -1,
            "maxBaseStations": -1,
            "maxCameras": 5,
            "maxSmartHomeModes": -1,
            "maxStorage": -1,
            "numPushNotify": -1,
            "planAmount": 0.0,
            "planCapacity": null,
            "planCurrencyAmount": "$0.00",
            "planId": "12345678",
            "planName": "Basic",
            "planType": "BASIC",
            "planUpgradeable": true,
            "plansTotalCurrencyAmount": "$0.00/Yr",
            "schedule": true,
            "scheduleExpiry": -1,
            "sharing": true,
            "sharingExpiry": -1,
            "term": 12,
            "userPreferences": {
                "alerts": {
                    "lowBatteryAlert": true,
                    "pushNotificationAlert": true,
                    "pushNotificationCount": -1,
                    "storageAlert": false
                },
                "storage": {
                    "autoDelete": false,
                    "enabled": true
                }
            }
        }
    ],
    "success": true
}
```
