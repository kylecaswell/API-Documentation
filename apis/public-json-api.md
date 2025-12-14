# Public Server Status JSON API

The Public Server Status JSON API gives you access to live server statuses. This API is public and **does not require a key** as this data is cached every second.

## API Index

We currently offer the following public JSON APIs:

| API | Description | Documentation |
| :--- | :--- | :--- |
| `/status_one.json` | CityDriving One Server Status | [View Docs](public-json-api.md#server-status-citydriving-one) |
| `/status_two.json` | CityDriving Two Server Status | [View Docs](public-json-api.md#server-status-citydriving-two) |

## Server Status: CityDriving One

**REQUEST:** `/json/status_one.json`

This request indexes players by InSim PLID \(inside the `players` object\) and returns all currently connected clients. It is designed for use with local InSim applications. This example only returns one client for brevity.

**RESPONSE:**

```text
GET https://world.city-driving.co.uk/api/v2/json/status_one.json
HTTP/1.1 200 OK
```

```javascript
{
  "t": 1765741124069,
  "n": "One",
  "tk": "AS5X",
  "ps": {
    "3": {
      "u": 3,
      "p": 6,
      "un": "robo1990",
      "nn": "^4ROBO^7™[COP]",
      "r": 2,
      "f": 1,
      "a": 0,
      "us": 0,
      "x": -438.54,
      "y": -634.26,
      "h": 22.44,
      "s": 0.0,
      "l": "Main St. South",
      "sl": 33.43,
      "bl": 54.74,
      "bc": 100.0,
      "sid": "2A1D5F",
      "v": "HUPUZ"
    },
        ...
    }
}
```

## Server Status: CityDriving Two

**REQUEST:** `/json/status_two.json`

This request indexes players by InSim PLID \(inside the `players` object\) and returns all currently connected clients. It is designed for use with local InSim applications. This example only returns one client for brevity.

**RESPONSE:**

```text
GET https://world.city-driving.co.uk/api/v2/json/status_two.json
HTTP/1.1 200 OK
```

```javascript
{
  "t": 1765741347519,
  "n": "Two",
  "tk": "AS5X",
  "ps": {
    "1": {
      "u": 1,
      "p": 117,
      "un": "Milkereus",
      "nn": "^7{SQUID}Revvy",
      "r": 1,
      "f": 1,
      "a": 0,
      "us": 0,
      "x": -627.43,
      "y": -224.89,
      "h": 178.45,
      "s": 8.18,
      "l": "^2Safe Zone",
      "sl": 0.0,
      "bl": 0.0,
      "bc": 0.0,
      "sid": "429F4A",
      "v": "KISOH"
    },
        ...
    }
}
```

