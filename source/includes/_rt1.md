<h1 id="logik-configurator-runtime-apis-v1-configuration">Configuration</h1>

Creating new configurations, reconfiguring existing configurations, making updates to a configuration and saving changes. Can be used for headless or custom UI implementations.

## Important Versioning Information

Blueprints that use Product Picker Fields ***must*** use the `application/vnd.logik.cfg-v2+json` Content-Type when making requests.

 The Runtime APIs are versioned using different Content-Types. There are 2 Content-Type formats, `application/json` for v1 and `application/vnd.logik.cfg-v2+json` for v2.

- `application/json`: can be used with regular Logik field types (number, boolean, text and picklist) and sets.
- `application/vnd.logik.cfg-v2+json`: can be used with all regular field types as well as Product Picker Fields.
  
The Accept Header should match the Content-Type being used, either:

- `application/json`: for v1.
- `application/vnd.logik.cfg-v2+json, application/json`: for v2.

## Start Configuration

<a id="opIdstartConfig"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "sessionContext": {
    "stateful": true
  },
  "partnerData": {
    "product": {
      "configuredProductId": "string",
      "configurationAttributes": {
        "LGK__ConfigurationId__c": "string"
      }
    }
  },
  "quote": {
    "SBQQ__PricebookId__c": "string"
  },
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = {
  "sessionContext": {
    "stateful": true
  },
  "partnerData": {
    "product": {
      "configuredProductId": "string",
      "configurationAttributes": {
        "LGK__ConfigurationId__c": "string"
      }
    }
  },
  "quote": {
    "SBQQ__PricebookId__c": "string"
  },
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api',
{
  method: 'POST',
  body: JSON.stringify(inputBody),
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```shell
# You can also use wget
curl -X POST https://{tenant}.{sector}.logik.io/api \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api HTTP/1.1

Content-Type: application/json
Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Origin' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Origin": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api`

Initialize a new Configuration or reconfigure an existing Configuration if passing an existing Logik Configuration UUID in the Request Body.

> Body parameter

```json
{
  "sessionContext": {
    "stateful": true
  },
  "partnerData": {
    "product": {
      "configuredProductId": "string",
      "configurationAttributes": {
        "LGK__ConfigurationId__c": "string"
      }
    }
  },
  "quote": {
    "SBQQ__PricebookId__c": "string"
  },
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
}
```

<h3 id="start-configuration-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|body|body|[InitConfig](#schemainitconfig)|false|Configurable Product Object to initialize|

> Example responses

> 200 Response

```json
{
  "fields": [
    {
      "value": "string",
      "dataType": "string",
      "visibilityState": "string",
      "editable": "string",
      "variableName": "string",
      "optionSet": {
        "options": [
          {
            "label": "string",
            "state": "string",
            "value": "string",
            "imageUrl": "string",
            "orderNumber": 0
          }
        ]
      }
    }
  ],
  "uuid": "string",
  "revision": 0,
  "valid": true,
  "messages": [
    {
      "message": "string",
      "type": "string",
      "error": true,
      "field": "string"
    }
  ],
  "productChange": true,
  "products": [
    {
      "id": "string",
      "selectionType": "string",
      "quantity": 0,
      "bomType": "string",
      "level": 0,
      "parentProduct": 0,
      "notes": "string",
      "uniqueIdentifier": 0,
      "description": "string",
      "externalId": "string",
      "name": "string",
      "price": 0,
      "extPrice": 0
    }
  ],
  "layouts": [
    {
      "url": "string"
    }
  ],
  "relatedChanges": [
    {
      "key": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="start-configuration-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return the state of configuration at initalization or reconfiguration. Includes fields, messages and products.|[ConfigResponse](#schemaconfigresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Configuration

<a id="opIdgetConfigByUuid"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```shell
# You can also use wget
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid} \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid} HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Origin' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Origin": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}`

Returns the Configuration state from the given Configuration UUID. This *does not* allow changes to made to the Configuration. To make changes, reconfigure using the POST call.

<h3 id="get-configuration-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|

> Example responses

> 200 Response

```json
{
  "fields": [
    {
      "value": "string",
      "dataType": "string",
      "visibilityState": "string",
      "editable": "string",
      "variableName": "string",
      "optionSet": {
        "options": [
          {
            "label": "string",
            "state": "string",
            "value": "string",
            "imageUrl": "string",
            "orderNumber": 0
          }
        ]
      }
    }
  ],
  "uuid": "string",
  "revision": 0,
  "valid": true,
  "messages": [
    {
      "message": "string",
      "type": "string",
      "error": true,
      "field": "string"
    }
  ],
  "productChange": true,
  "products": [
    {
      "id": "string",
      "selectionType": "string",
      "quantity": 0,
      "bomType": "string",
      "level": 0,
      "parentProduct": 0,
      "notes": "string",
      "uniqueIdentifier": 0,
      "description": "string",
      "externalId": "string",
      "name": "string",
      "price": 0,
      "extPrice": 0
    }
  ],
  "layouts": [
    {
      "url": "string"
    }
  ],
  "relatedChanges": [
    {
      "key": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="get-configuration-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return initial state of fields, messages and products|[ConfigResponse](#schemaconfigresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Update or Save Configuration

<a id="opIdupdateConfigByUuid"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('https://{tenant}.{sector}.logik.io/api/{uuid}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = {
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}',
{
  method: 'PATCH',
  body: JSON.stringify(inputBody),
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```shell
# You can also use wget
curl -X PATCH https://{tenant}.{sector}.logik.io/api/{uuid} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH https://{tenant}.{sector}.logik.io/api/{uuid} HTTP/1.1

Content-Type: application/json
Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Origin' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'https://{tenant}.{sector}.logik.io/api/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Origin": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://{tenant}.{sector}.logik.io/api/{uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/{uuid}`

Update or Save Configuration with the provided Configuration UUID.

> Body parameter

```json
{
  "fields": [
    {
      "variableName": "string",
      "value": "string"
    }
  ]
}
```

<h3 id="update-or-save-configuration-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|delta|query|boolean|false|If `delta=true` the API only retruns changed data. This is default behavior of the API if the parameter is omitted.|
|save|query|boolean|false|Pass save parameter as true to save the Configuration and send BOM to connected application|
|body|body|[UpdateConfig](#schemaupdateconfig)|true|Update or Save Payload for a Configuration.|

> Example responses

> 200 Response

```json
{
  "fields": [
    {
      "value": "string",
      "dataType": "string",
      "visibilityState": "string",
      "editable": "string",
      "variableName": "string",
      "optionSet": {
        "options": [
          {
            "label": "string",
            "state": "string",
            "value": "string",
            "imageUrl": "string",
            "orderNumber": 0
          }
        ]
      }
    }
  ],
  "uuid": "string",
  "revision": 0,
  "valid": true,
  "messages": [
    {
      "message": "string",
      "type": "string",
      "error": true,
      "field": "string"
    }
  ],
  "productChange": true,
  "products": [
    {
      "id": "string",
      "selectionType": "string",
      "quantity": 0,
      "bomType": "string",
      "level": 0,
      "parentProduct": 0,
      "notes": "string",
      "uniqueIdentifier": 0,
      "description": "string",
      "externalId": "string",
      "name": "string",
      "price": 0,
      "extPrice": 0
    }
  ],
  "layouts": [
    {
      "url": "string"
    }
  ],
  "relatedChanges": [
    {
      "key": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="update-or-save-configuration-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns state of fields, messages and products|[ConfigResponse](#schemaconfigresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Set

<a id="opIdgetSet"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}', params={
  'page': '0',  'limit': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}?page=0&limit=100&sort=modified%2CDESC',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Origin':'string',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}?page=0&limit=100&sort=modified%2CDESC',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```shell
# You can also use wget
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}?page=0&limit=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}?page=0&limit=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}?page=0&limit=100&sort=modified%2CDESC");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Origin' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}',
  params: {
  'page' => 'number',
'limit' => 'number',
'sort' => 'string'
}, headers: headers

p JSON.parse(result)

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Origin": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}/sets/{setVariableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}/sets/{setVariableName}`

Access fields in a given Set. Use if Set flagged in relatedChanges param

<h3 id="get-set-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|setVariableName|path|string|true|Variable name of the Set defined in admin for which data is requested|
|page|query|number|true|Page number of results to return|
|limit|query|number|true|Size of the paged data results|
|sort|query|string|true|Sort field and order of the results, specify property and order{asc|desc} of sort in format field,asc[desc]|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "index": 0,
      "fields": [
        {
          "value": "string",
          "dataType": "string",
          "visibilityState": "string",
          "editable": "string",
          "variableName": "string",
          "optionSet": {
            "options": [
              {
                "label": "string",
                "state": "string",
                "value": "string",
                "imageUrl": "string",
                "orderNumber": 0
              }
            ]
          }
        }
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "totalPages": 0,
  "totalElements": 0,
  "last": true,
  "size": 0,
  "number": 0,
  "numberOfElements": 0,
  "first": true,
  "empty": true,
  "total": 0
}
```

<h3 id="get-set-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Paginated details for a given Set variable name|[SetsResponse](#schemasetsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>
