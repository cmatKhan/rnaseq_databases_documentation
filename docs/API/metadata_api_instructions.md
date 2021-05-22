# Database API

If you are a development user, then the easiest way to interact with a database will be by remotely connecting to the database with either Python or R (see [R DBI package](https://dbi.r-dbi.org/)).

The following http requests are supported:  

## OPTIONS

An options requests returns metadata about a given table.  

Sample output:  

```json
Content-Type application/json

{
    "name": "Bio Sample List",
    "description": "foreign_key: None",
    "renders": [
        "application/json",
        "text/html"
    ],
    "parses": [
        "application/json",
        "application/x-www-form-urlencoded",
        "multipart/form-data"
    ],
    "actions": {
        "POST": {
            "bioSampleNumber": {
                "type": "integer",
                "required": false,
                "read_only": true,
                "label": "BioSampleNumber"
            },
            "harvestDate": {
                "type": "date",
                "required": false,
                "read_only": false,
                "label": "HarvestDate"
            },
            "harvester": {
                "type": "choice",
                "required": true,
                "read_only": false,
                "label": "Harvester",
                "choices": [
                    {
                        "value": "H.BROWN",
                        "display_name": "H.BROWN"
                    },
                    {
                        "value": "J.PLAGGENBERG",
                        "display_name": "J.PLAGGENBERG"
                    },
                    {
                        "value": "D.AGUSTINHO",
                        "display_name": "D.AGUSTINHO"
                    },
                    {
                        "value": "S.GISH",
                        "display_name": "S.GISH"
                    }
                ]
            },
            ...
```

### OPTIONS: Python

```python
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.options(url, headers=headers)
```

### OPTIONS: Node.js/Axios

```javascript
import axios

const url = 'http://127.0.0.1:8000/api/v1/BioSample'
const token = "laksjdflaskjdflasdjkf"

axios.options(url, {
  headers: {
    'Authorization': `Token ${token}`
  },
})

```

## GET

Get requests will return data from the database

Sample output:  

```json
Content-Type application/json
201 Created

{
    "count": 587,
    "next": "http://127.0.0.1:8000/api/v1/BioSample/?page=2",
    "previous": null,
    "results": [
        {
            "bioSampleNumber": 1,
            "harvestDate": "2019-05-17",
            "harvester": "J.PLAGGENBERG",
            "experimentDesign": "ZEV_flood_media_delay_2",
            "experimentObservations": "",
            "bioSampleObservations": "",
            ...
        },
        {
            "bioSampleNumber": 2,
            "harvestDate": "2019-05-17",
            "harvester": "J.PLAGGENBERG",
            "experimentDesign": "ZEV_flood_media_delay_2",
            "experimentObservations": "",
            "bioSampleObservations": "",
            ...
}
```

### GET: Python

```python
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.get(url, headers=headers)
```

### GET: Node.js/Axios

```javascript
import axios

const url = 'http://127.0.0.1:8000/api/v1/BioSample'
const token = "laksjdflaskjdflasdjkf"

axios.get(url, {
  headers: {
    'Authorization': `Token ${token}`
  },
})

```

## POST

### POST: Node.js/Axios

```javascript
import axios

const url = 'http://127.0.0.1:8000/api/v1/BioSample'
const data = {
  ...
}

axios.post(url, data, {
  headers: {
    'Authorization': `Token ${token}`
  },
})
```

## PUT/PATCH

[See here for an explanation of the difference between put and patch](https://rapidapi.com/blog/put-vs-patch/)

### PUT: Node.js/Axios

```javascript
import axios

const url = 'http://127.0.0.1:8000/api/v1/BioSample'
const data = {
  ...
}

axios.patch(url, data, {
  headers: {
    'Authorization': `Token ${token}`
  },
})

```

### PATCH: Node.js/Axios

```javascript
import axios

const url = 'http://127.0.0.1:8000/api/v1/BioSample'
const data = {
  ...
}

axios.put(url, data, {
  headers: {
    'Authorization': `Token ${token}`
  },
})

```
