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
        "email": "han@example.com",
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
## Payment offers
GET https://arlo.netgear.com/hmsweb/users/payment/offers
```
{
    "data": [
        {
            "alertLowBattery": -1,
            "alertStorage": 0,
            "amount": "$0.00",
            "amountRaw": 0.0,
            "autoManageStorageExpiry": -1,
            "comments": "",
            "countryCode": "US",
            "createdDate": 1500397465452,
            "currency": "usd",
            "cvrAccessExpiry": 7,
            "groupName": "Basic",
            "groupNumber": 0,
            "id": "planId",
            "lastModified": 1500397465452,
            "libraryAccessExpiry": 7,
            "maxStorage": -1,
            "numAccounts": -1,
            "numBaseStationsSupported": -1,
            "numCamerasSupported": 5,
            "numPushNotify": -1,
            "numSmartHomeModes": -1,
            "planDescription": "Basic Plan - US",
            "planId": "12345678",
            "planMinutes": 0,
            "planName": "Basic",
            "planType": "BASIC",
            "scheduleExpiry": -1,
            "sharingExpiry": -1,
            "storageAutoDelete": 0,
            "term": "12",
            "tieredAmount": "{}"
        },
        ...
    ],
    "success": true
}
```
## Profile
GET https://arlo.netgear.com/hmsweb/users/profile
```
{
    "data": {
        "_type": "User",
        "acceptedPolicy": 1,
        "country": "US",
        "currentPolicy": 1,
        "firstName": "Han",
        "language": "en",
        "lastName": "Solo",
        "validEmail": true
    },
    "success": true
}
```
## Friends
GET https://arlo.netgear.com/hmsweb/users/friends
```
{
    "data": [
        {
            "adminUser": false,
            "createdDate": 1500004426332,
            "devices": [
                {
                    "deviceId": "ABC",
                    "deviceName": "Back yard",
                    "modifiedDate": 1500004426332,
                    "uniqueId": "ABCDE-123-12345678_ABCDEF1234567"
                },
                {
                    "deviceId": "4XH4767WA1D1A",
                    "deviceName": "Side",
                    "modifiedDate": 1500004426332,
                    "uniqueId": "ABCDE-123-12345678_ABCDEF1234567"
                },
                {
                    "deviceId": "4XH4767CA37E9",
                    "deviceName": "Front door",
                    "modifiedDate": 1500004426332,
                    "uniqueId": "ABCDE-123-12345678_ABCDEF1234567"
                }
            ],
            "email": "luke@example.com",
            "firstName": "Luke",
            "lastModified": 1500004426332,
            "lastName": "Skywalker",
            "status": "ACCEPTED|EXPIRED"
        },
        ...
    ],
    "success": true
}
```
## Devices
GET https://arlo.netgear.com/hmsweb/users/devices
```
{
    "data": [
        {
            "connectivity": {
                "connected": true,
                "type": "ethernet"
            },
            "deviceId": "XXX",
            "deviceName": "Millenium Falcon",
            "deviceType": "basestation",
            "displayOrder": 3,
            "interfaceSchemaVer": "1",
            "interfaceVersion": "i000",
            "lastModified": 1501195843521,
            "mediaObjectCount": 0,
            "modelId": "VMB4000",
            "owner": {
                "firstName": "Han",
                "lastName": "Solo",
                "ownerId": "XXX"
            },
            "properties": {
                "hwVersion": "VMB4000r3",
                "modelId": "VMB4000",
                "olsonTimeZone": "America/Los_Angeles"
            },
            "state": "provisioned",
            "uniqueId": "XXX",
            "userId": "XXX",
            "userRole": "OWNER",
            "xCloudId": "XXX"
        },
        {
            "deviceId": "XXX",
            "deviceName": "Cockpit",
            "deviceType": "siren",
            "displayOrder": 5,
            "interfaceSchemaVer": "1",
            "interfaceVersion": "i000",
            "mediaObjectCount": 0,
            "modelId": "VMB4000-siren",
            "owner": {
                "firstName": "Han",
                "lastName": "Solo",
                "ownerId": "XXX"
            },
            "parentId": "XXX",
            "state": "provisioned",
            "uniqueId": "XXX",
            "userId": "XXX",
            "userRole": "OWNER",
            "xCloudId": "XXX"
        },
        {
            "deviceId": "XXX",
            "deviceName": "Pilot",
            "deviceType": "camera",
            "displayOrder": 4,
            "interfaceSchemaVer": "2",
            "interfaceVersion": "i002",
            "lastImageUploaded": "true",
            "lastModified": 1501195843521,
            "mediaObjectCount": 0,
            "modelId": "VMC4030",
            "owner": {
                "firstName": "Han",
                "lastName": "Solo",
                "ownerId": "XXX"
            },
            "parentId": "XXX",
            "presignedFullFrameSnapshotUrl": "https://...",
            "presignedLastImageUrl": "https://...",
            "presignedSnapshotUrl": "...",
            "properties": {
                "hwVersion": "H8",
                "modelId": "VMC4030",
                "olsonTimeZone": "America/Los_Angeles"
            },
            "state": "provisioned",
            "uniqueId": "XXX",
            "userId": "XXX",
            "userRole": "OWNER",
            "xCloudId": "XXX"
        },
        ...
    ],
    "success": true
}
```
