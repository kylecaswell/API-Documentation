# User Profile API

The endpoint for the user profile API is: `/citydriving/profile`

## API Index

We currently offer the following user profile APIs:

| API | Documentation |
| :--- | :--- |
| Get a User Profile | [View Docs](user-profile-api.md#get-a-user-profile) |

## Get a User Profile

Access all of a CityDriving user's profile details and statistics.

**ENDPOINT:** `/citydriving/profile/get`

### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `username` | _{string}_ : A Live for Speed username |

### Optional Parameters

This API can optionally return a stats object, an array of cars \(with or without their upgrades\), an array of licences and/or and array of properties. Any combination can be requested.

| Name | Expected Value |
| :--- | :--- |
| `stats` | _{number}_ : 0 \| 1 |
| `cars` | _{number}_ : 0 \| 1 |
| `licenses` | _{number}_ : 0 \| 1 |
| `upgrades` | _{number}_ : 0 \| 1 |
| `properties` | _{number}_ : 0 \| 1 |

### Example

**REQUEST:** 

```text
?key=YOUR_KEY&username=chucknorris&stats=1&cars=1&licenses=1&upgrades=1&properties=1
```

This request usually returns all cars, licenses, properties and upgrades owned by a user. This example only shows one of each type for brevity.

**RESPONSE:**

```text
GET https://world.city-driving.co.uk/api/v2/citydriving/profile/get?key=YOUR_KEY&username=chucknorris&stats=1&cars=1&licenses=1&upgrades=1&properties=1
HTTP/1.1 200 OK
```

```javascript
{
  "id": 4,
  "username": "chucknorris",
  "isOnline": true,
  "nickname": "^7‹Chuck›",
  "insimAdmin": true,
  "adminLevel": 1,
  "needsCopTraining": false,
  "money": 19988,
  "dateJoined": "2007-12-21T20:18:10+00:00",
  "dateLastSeen": "2021-03-06T17:33:38+00:00",
  "countryCode": "de",
  "flag": "//cdn.boardhost.com/flags/de.png",
  "stats": {
    "1": 452703,
    "2": 882887,
    "3": 16240,
    "4": 47884,
    "5": 3087,
    "6": 225626,
    "7": 8526
  },
  "licences": [
    {
      "id": "cop",
      "name": "Cop License",
      "dateIssued": "2019-08-03T12:14:08+00:00",
      "validUntil": "2020-08-02T12:14:08+00:00",
      "suspendedUntil": null,
      "revoked": false,
      "expired": true,
      "suspended": false
    }
  ],
  "properties": [
    {
      "id": 126019,
      "type": "ramp",
      "name": "Ramp",
      "condition": 0.4415,
      "value": 1104
    }
  ],
  "cars": [
    {
      "vin": "ACSRK",
      "type": "UF1.XMAS",
      "odometerKm": 767.235,
      "condition": 95.49,
      "wear": 4.149,
      "damage": 0.3526,
      "upgrades": [
        {
          "id": 126019,
          "type": "ramp",
          "name": "Ramp",
          "condition": 0.4415,
          "value": 1104
        }
      ]
    }
  ]
}
```

