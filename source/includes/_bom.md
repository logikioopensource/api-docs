<h1 id="logik-bom-runtime-apis-v1-bill-of-materials">Bill of Materials</h1>

Get Bill of Materials (BOM) information for a given configuration UUID.

## Get BOM

<a id="opIdgetAllBom"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}/bom', params={
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom?page=0&limit=100&sort=modified%2CDESC',
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom?page=0&limit=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom?page=0&limit=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom?page=0&limit=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}/bom?page=0&limit=100&sort=modified%2CDESC");
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

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}/bom',
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
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}/bom", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}/bom`

Get BOM with the given uuid for current state of Configuration

<h3 id="get-bom-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|page|query|number|true|Page number of results to return|
|limit|query|number|true|Size of the paged data results|
|sort|query|string|true|Sort field and order of the results, specify property and order{asc|desc} of sort in format field,asc[desc]|
|bomType|query|string|false|Pass comma separated list of bom types to be returned|

> Example responses

> 200 Response

```json
{
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
      "extPrice": 0,
      "extended": {
        "additionalProperties": "string"
      }
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

<h3 id="get-bom-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return Entire BOM snapshot of Configuration|[BOMResponse](#schemabomresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Sales BOM

<a id="opIdgetSalesBom"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales', params={
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales?page=0&limit=100&sort=modified%2CDESC',
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales?page=0&limit=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales?page=0&limit=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales?page=0&limit=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales?page=0&limit=100&sort=modified%2CDESC");
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

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales',
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
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}/bom/sales", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}/bom/sales`

Get Sales BOM with the given uuid for current state of Configuration

<h3 id="get-sales-bom-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|page|query|number|true|Page number of results to return|
|limit|query|number|true|Size of the paged data results|
|sort|query|string|true|Sort field and order of the results, specify property and order{asc|desc} of sort in format field,asc[desc]|

> Example responses

> 200 Response

```json
{
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
      "extPrice": 0,
      "extended": {
        "additionalProperties": "string"
      }
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

<h3 id="get-sales-bom-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return current sales BOM of Configuration|[BOMResponse](#schemabomresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Manufacturing BOM

<a id="opIdgetManufacturingBom"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing', params={
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing?page=0&limit=100&sort=modified%2CDESC',
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing?page=0&limit=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing?page=0&limit=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing?page=0&limit=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing?page=0&limit=100&sort=modified%2CDESC");
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

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing',
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
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}/bom/manufacturing", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}/bom/manufacturing`

Get Manufacturing BOM with the given uuid for current state of Configuration.

<h3 id="get-manufacturing-bom-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|page|query|number|true|Page number of results to return|
|limit|query|number|true|Size of the paged data results|
|sort|query|string|true|Sort field and order of the results, specify property and order{asc|desc} of sort in format field,asc[desc]|

> Example responses

> 200 Response

```json
{
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
      "extPrice": 0,
      "extended": {
        "additionalProperties": "string"
      }
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

<h3 id="get-manufacturing-bom-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return Manufacturing BOM snapshot of Configuration|[BOMResponse](#schemabomresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Custom BOM

<a id="opIdgetBomByName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}', params={
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}?page=0&limit=100&sort=modified%2CDESC',
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

fetch('https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}?page=0&limit=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}?page=0&limit=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}?page=0&limit=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json
Origin: string

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}?page=0&limit=100&sort=modified%2CDESC");
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

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}',
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
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/{uuid}/bom/{custom}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/{uuid}/bom/{custom}`

Get Custom BOM type line items defined in the admin

<h3 id="get-custom-bom-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|custom|path|string|true|Custom BOM Type name|
|uuid|path|string|true|Unique Configuration ID Value|
|page|query|number|true|Page number of results to return|
|limit|query|number|true|Size of the paged data results|
|sort|query|string|true|Sort field and order of the results, specify property and order{asc|desc} of sort in format field,asc[desc]|

> Example responses

> 200 Response

```json
{
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
      "extPrice": 0,
      "extended": {
        "additionalProperties": "string"
      }
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

<h3 id="get-custom-bom-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns BOM snapshot of Configuration|[BOMResponse](#schemabomresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>
