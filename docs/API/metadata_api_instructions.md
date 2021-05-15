## Add data to a table

**Request**:

`OPTIONS` `/api/v1/<tablename> Authorization: Token: somerandomstringofstuff`

###### Python

```
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.get(url, headers=headers)
```

`GET` `/api/v1/<tablename> Authorization: Token: somerandomstringofstuff`

###### Python

```
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.get(url, headers=headers)
```

`POST` `/api/v1/<tablename> Authorization: Token: somerandomstringofstuff`

###### Node.js/Axios

```
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

`PATCH` `/api/v1/<tablename> Authorization: Token: somerandomstringofstuff`

###### Python

```
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.get(url, headers=headers)
```

`DELETE` `/api/v1/<tablename> Authorization: Token: somerandomstringofstuff`

###### Python

```
import requests

url = 'http://127.0.0.1:8000/api/v1/BioSample/'
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}
r = requests.get(url, headers=headers)
```

*Note:*

- Authorization Protected

**Response**: `OPTIONS`
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

**Response**: `GET`

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