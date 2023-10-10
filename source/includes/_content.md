<h1 id="logik-io-admin-api-blueprints-blueprint">Blueprint</h1>

Blueprints

## Get List of Blueprints

<a id="opIdgetBlueprints"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/blueprints`

<h3 id="get-list-of-blueprints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 12,
      "name": "PC Builder",
      "variableName": "pCBuilder",
      "description": "",
      "modified": "2023-09-13T16:21:28.590092Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 18,
      "name": "newBP",
      "variableName": "newBP",
      "description": "ls",
      "modified": "2023-09-11T20:55:11.005400Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 8,
      "name": "ComputerBP",
      "variableName": "pickerGeneral",
      "description": "",
      "modified": "2023-09-07T13:49:40.877294Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 14,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 14,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-blueprints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of Blueprints|[BlueprintListResponse](#schemablueprintlistresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Blueprint

<a id="opIdgetBlueprintByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}`

<h3 id="get-a-blueprint-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|

> Example responses

> 200 Response

```json
{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "endDate",
    "pleExtension"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-15T17:39:47.990406Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}
```

<h3 id="get-a-blueprint-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Details about a specific blueprint|[BlueprintResponse](#schemablueprintresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Blueprint

<a id="opIdputBlueprintByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "textTest_swc",
    "endDate",
    "pleExtension",
    "hidden_sc",
    "startDate",
    "pricer_sc",
    "cpuPicker"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-13T16:21:28.590092Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
{
  method: 'PUT',
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
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "textTest_swc",
    "endDate",
    "pleExtension",
    "hidden_sc",
    "startDate",
    "pricer_sc",
    "cpuPicker"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-13T16:21:28.590092Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v1/blueprints/{blueprintName}`

> Body parameter

```json
{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "textTest_swc",
    "endDate",
    "pleExtension",
    "hidden_sc",
    "startDate",
    "pricer_sc",
    "cpuPicker"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-13T16:21:28.590092Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}
```

<h3 id="update-a-blueprint-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|body|body|[Blueprint](#schemablueprint)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "textTest_swc",
    "endDate",
    "pleExtension",
    "hidden_sc",
    "startDate",
    "pricer_sc",
    "cpuPicker"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-13T16:21:28.590092Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}
```

<h3 id="update-a-blueprint-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated Blueprint Data|[Blueprint](#schemablueprint)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete a Blueprint

<a id="opIddeleteBlueprintByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName} HTTP/1.1

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/v1/blueprints/{blueprintName}`

<h3 id="delete-a-blueprint-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|

<h3 id="delete-a-blueprint-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-blueprint-details">Blueprint > Details</h1>

Retrieve and update Blueprint details

## Get Blueprint Available Fields

<a id="opIdgetBlueprintAvailableFields"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields', params={
  'page': '0',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields?page=0&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields?page=0&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields?page=0&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields?page=0&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields?page=0&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields',
  params: {
  'page' => 'number',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/availableFields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/blueprints/{blueprintName}/availableFields`

Returns a list of Available Fields that can be associated with the blueprint

<h3 id="get-blueprint-available-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 303,
      "name": "jacksonFakeField10",
      "variableName": "jacksonFakeField10",
      "description": null,
      "type": "Number",
      "modified": "2023-07-11T16:32:35.498893Z",
      "category": "USER",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 323,
      "name": "FletchTestPicker2",
      "variableName": "fletchTestPicker2",
      "description": null,
      "type": "ProductPicker",
      "modified": "2023-07-17T23:00:27.861311Z",
      "category": "PRODUCT_PICKER",
      "selectType": "multi",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 281,
      "name": "jacksonPolicy",
      "variableName": "jacksonPolicy",
      "description": null,
      "type": "Picklist",
      "modified": "2023-07-05T13:47:14.613554Z",
      "category": "USER",
      "selectType": "single",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 62,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 62,
  "first": true,
  "empty": false
}
```

<h3 id="get-blueprint-available-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintAvailableFieldsResponse](#schemablueprintavailablefieldsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Enrichment Scripts

<a id="opIdgetBlueprintScripts"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/scripts`

Get Enrichment Scripts for a Blueprint

<h3 id="get-enrichment-scripts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|

> Example responses

> 200 Response

```json
[
  {
    "created": "2023-09-15T17:40:39.187492Z",
    "modified": "2023-09-15T17:40:39.187492Z",
    "id": 9,
    "scriptArea": "INIT",
    "script": {
      "created": "2023-09-15T17:40:39.199291Z",
      "modified": "2023-09-15T17:40:39.199291Z",
      "id": 41,
      "content": "var x=1;\nreturn cfgRequest;",
      "returnType": "map"
    },
    "runOnDemand": false,
    "forcedOnDemand": false
  }
]
```

<h3 id="get-enrichment-scripts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintScriptListResponse](#schemablueprintscriptlistresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create an Enrichment Script

<a id="opIdpostBlueprintScript"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "script": {
    "content": "var x=1;\nreturn cfgRequest;",
    "returnType": "map"
  },
  "runOnDemand": false
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}',
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
  "script": {
    "content": "var x=1;\nreturn cfgRequest;",
    "returnType": "map"
  },
  "runOnDemand": false
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/blueprints/{blueprintName}/scripts/{scriptType}`

> Body parameter

```json
{
  "script": {
    "content": "var x=1;\nreturn cfgRequest;",
    "returnType": "map"
  },
  "runOnDemand": false
}
```

<h3 id="create-an-enrichment-script-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|scriptType|path|string|true|none|
|body|body|[BlueprintEnrichmentScript](#schemablueprintenrichmentscript)|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|scriptType|INIT|
|scriptType|PRODUCT|
|scriptType|PRICING|
|scriptType|VALIDATION|

> Example responses

> 201 Response

```json
{
  "created": "2023-09-15T17:40:39.187492435Z",
  "modified": "2023-09-15T17:40:39.187492435Z",
  "id": 9,
  "scriptArea": "INIT",
  "script": {
    "created": "2023-09-15T17:40:39.199291228Z",
    "modified": "2023-09-15T17:40:39.199291228Z",
    "id": 41,
    "content": "var x=1;\nreturn cfgRequest;",
    "returnType": "map",
    "compileWarnings": []
  },
  "runOnDemand": false,
  "forcedOnDemand": false
}
```

<h3 id="create-an-enrichment-script-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-an-enrichment-script-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» scriptArea|string|false|none|none|
|» script|object|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» content|string|false|none|none|
|»» returnType|string|false|none|none|
|»» compileWarnings|[any]|false|none|none|
|» runOnDemand|boolean|false|none|none|
|» forcedOnDemand|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-blueprint-related">Blueprint > Related</h1>

Retrieve related Blueprint information

## Get Related Fields

<a id="opIdgetBlueprintRelatedFields"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/fields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/blueprints/{blueprintName}/fields`

Get Fields related to a Blueprint

<h3 id="get-related-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "type": "Picklist",
      "created": "2023-06-08T14:16:59.580802Z",
      "modified": "2023-08-09T14:29:01.175031Z",
      "id": 115,
      "name": "Motherboard Selection",
      "variableName": "pleExtension",
      "description": null,
      "required": true,
      "category": "USER",
      "hasExtension": true,
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "selectType": "single",
      "defaultValue": null
    },
    {
      "type": "Boolean",
      "created": "2023-06-02T19:01:43.730714Z",
      "modified": "2023-07-19T21:48:44.395142Z",
      "id": 91,
      "name": "hidden_sc",
      "variableName": "hidden_sc",
      "description": null,
      "required": false,
      "category": "USER",
      "lastModifiedBy": "scheck.dev (API)",
      "trueLabel": "yes",
      "falseLabel": "no",
      "defaultValue": false
    },
    {
      "type": "Picklist",
      "created": "2023-05-22T20:30:00.044552Z",
      "modified": "2023-07-19T21:48:44.353860Z",
      "id": 19,
      "name": "CPU Type",
      "variableName": "cPUType",
      "description": null,
      "required": false,
      "category": "USER",
      "lastModifiedBy": "scheck.dev (API)",
      "selectType": "single",
      "defaultValue": null
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 6,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 6,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintRelatedFieldsResponse](#schemablueprintrelatedfieldsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Configurable Products

<a id="opIdgetBlueprintRelatedProducts"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/configurableProducts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/configurableProducts`

Get Configurable Products related to a Blueprint

<h3 id="get-related-configurable-products-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-06-14T14:55:49.699022Z",
      "modified": "2023-06-21T22:23:09.801284Z",
      "id": 3,
      "name": "UniqueLinesConfig",
      "blueprintVariableName": "pCBuilder",
      "partnerProductId": "01t6e000009bzMuAAI"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-configurable-products-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RelatedConfigProductsResponse](#schemarelatedconfigproductsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Sets

<a id="opIdgetBlueprintRelatedSets"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/sets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/sets`

Get Sets related to a Blueprint

<h3 id="get-related-sets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 2,
      "name": "delta",
      "variableName": "delta",
      "sizeType": "setField",
      "created": "2023-06-07T22:34:50.052615Z",
      "modified": "2023-06-12T21:37:21.879233Z",
      "fields": [
        {
          "id": 9,
          "variableName": "textTest_swc",
          "name": "textTest_swc",
          "description": null,
          "type": "Text",
          "distinct": false,
          "created": "2023-06-12T21:37:21.877152Z",
          "modified": "2023-06-12T21:37:21.877152Z",
          "lastModifiedBy": "scheck.dev (API)"
        },
        {
          "id": 7,
          "variableName": "set.delta.index",
          "name": "Index for delta",
          "description": null,
          "type": "Number",
          "distinct": false,
          "created": "2023-06-12T21:36:46.256658Z",
          "modified": "2023-06-12T21:37:21.879317Z",
          "lastModifiedBy": null
        }
      ],
      "aggregateFields": [
        {
          "type": "Number",
          "created": "2023-06-12T21:37:11.596742Z",
          "modified": "2023-06-12T21:37:11.596742Z",
          "id": 135,
          "name": "count",
          "variableName": "set.delta.count",
          "description": null,
          "required": false,
          "category": "SET_AGGREGATE",
          "setVariableName": "delta",
          "aggregateType": "COUNT",
          "fieldVariableNames": [
            "textTest_swc"
          ],
          "lastModifiedBy": "scheck@cpq1.logik.dev",
          "defaultValue": null,
          "unitLabel": null,
          "precision": 32,
          "minValue": null,
          "maxValue": null,
          "stepValue": null
        }
      ],
      "sizeFieldVariableName": "set.delta.size",
      "sizeField": {
        "type": "Size",
        "created": "2023-06-07T22:34:50.052776Z",
        "modified": "2023-06-07T22:34:50.063657Z",
        "id": 114,
        "name": "delta Size",
        "variableName": "set.delta.size",
        "description": null,
        "required": false,
        "category": "SET_SIZE",
        "setVariableName": "delta",
        "lastModifiedBy": null,
        "defaultValue": null,
        "minValue": null,
        "maxValue": null
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-sets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintRelatedSetsResponse](#schemablueprintrelatedsetsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Product Pickers

<a id="opIdgetBlueprintRelatedProductPickers"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/productPickers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/productPickers`

Get Product Pickers related to a Blueprint

<h3 id="get-related-product-pickers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-06-13T21:28:17.672892Z",
      "modified": "2023-08-10T21:25:27.253738Z",
      "id": 147,
      "name": "cpuPicker",
      "variableName": "cpuPicker",
      "description": null,
      "required": false,
      "category": "PRODUCT_PICKER",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "selectType": "single",
      "enrichEnabled": false,
      "quantitySelectionLinked": true,
      "defaultType": null,
      "defaultBomType": null,
      "defaultParentProduct": "motherboard",
      "defaultUom": null,
      "defaultPricingProductSellingModelId": null,
      "defaultPricingStartDate": null,
      "defaultPricingEndDate": null,
      "layoutProductDetails": [
        "name"
      ],
      "fields": [
        {
          "created": "2023-06-21T22:07:38.272409Z",
          "modified": "2023-06-21T22:07:38.272409Z",
          "id": 117,
          "variableName": "cpuPicker.multiThreading",
          "label": "MultiThreading",
          "fieldType": "Boolean",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-21T22:11:25.996353Z",
          "modified": "2023-06-21T22:11:25.996353Z",
          "id": 119,
          "variableName": "cpuPicker.speed",
          "label": "speed",
          "fieldType": "Picklist",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.675998Z",
          "modified": "2023-06-13T21:28:17.675998Z",
          "id": 87,
          "variableName": "cpuPicker.value",
          "label": "Value",
          "fieldType": "Text",
          "target": "ProductId",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.680095Z",
          "modified": "2023-06-13T21:28:17.680095Z",
          "id": 88,
          "variableName": "cpuPicker.select",
          "label": "Select",
          "fieldType": "Boolean",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.683457Z",
          "modified": "2023-06-13T21:28:17.683457Z",
          "id": 89,
          "variableName": "cpuPicker.quantity",
          "label": "Quantity",
          "fieldType": "Number",
          "target": "ProductQuantity",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.759893Z",
          "modified": "2023-06-13T21:28:17.759893Z",
          "id": 91,
          "variableName": "cpuPicker.imageUrl",
          "label": "imageUrl",
          "fieldType": "Text",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-09T15:45:24.420897Z",
          "modified": "2023-08-09T15:45:24.420897Z",
          "id": 206,
          "variableName": "cpuPicker.description",
          "label": "description",
          "fieldType": "Text",
          "target": "ProductDescription",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-09T15:45:40.624501Z",
          "modified": "2023-08-09T15:45:40.624501Z",
          "id": 207,
          "variableName": "cpuPicker.price",
          "label": "price",
          "fieldType": "Number",
          "target": "ProductPrice",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-30T17:16:12.503744Z",
          "modified": "2023-08-30T17:16:12.503744Z",
          "id": 215,
          "variableName": "cpuPicker.wattage",
          "label": "wattage",
          "fieldType": "Number",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        }
      ],
      "rules": [
        {
          "created": "2023-06-13T21:34:48.695916Z",
          "modified": "2023-06-13T21:34:48.695916Z",
          "id": 77,
          "variableName": "inclusionTest",
          "type": "Inclusion",
          "status": "active",
          "columns": [
            {
              "id": 290,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 291,
              "header": "cPUType",
              "mappedFieldVarName": "cPUType",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            }
          ]
        },
        {
          "created": "2023-08-09T15:45:54.465480Z",
          "modified": "2023-08-09T15:45:54.465480Z",
          "id": 123,
          "variableName": "setInfo",
          "type": "Determination",
          "status": "active",
          "columns": [
            {
              "id": 438,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 439,
              "header": "cpuPicker.description",
              "mappedFieldVarName": "cpuPicker.description",
              "columnUse": "ProductDescription",
              "orderNumber": 1
            },
            {
              "id": 440,
              "header": "cpuPicker.price",
              "mappedFieldVarName": "cpuPicker.price",
              "columnUse": "ProductPrice",
              "orderNumber": 2
            }
          ]
        },
        {
          "created": "2023-06-21T22:11:42.152660Z",
          "modified": "2023-06-21T22:16:31.251965Z",
          "id": 89,
          "variableName": "limitCPUs",
          "type": "Quantity",
          "status": "active",
          "columns": [
            {
              "id": 330,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 331,
              "header": "pleExtension",
              "mappedFieldVarName": "pleExtension",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            },
            {
              "id": 332,
              "header": "quantity.min",
              "mappedFieldVarName": "quantity.min",
              "columnUse": "Field",
              "orderNumber": 2
            },
            {
              "id": 333,
              "header": "quantity.max",
              "mappedFieldVarName": "quantity.max",
              "columnUse": "Field",
              "orderNumber": 3
            },
            {
              "id": 334,
              "header": "quantity.step",
              "mappedFieldVarName": "quantity.step",
              "columnUse": "Field",
              "orderNumber": 4
            }
          ]
        },
        {
          "created": "2023-08-09T15:58:50.720599Z",
          "modified": "2023-08-09T16:06:01.950247Z",
          "id": 124,
          "variableName": "predef",
          "type": "Determination",
          "message": "Action is inactive because it includes fields not associated with the current blueprint (preconfigured).",
          "status": "invalid",
          "columns": [
            {
              "id": 441,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 442,
              "header": "preconfigured",
              "mappedFieldVarName": "preconfigured",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            },
            {
              "id": 443,
              "header": "cpuPicker.select",
              "mappedFieldVarName": "cpuPicker.select",
              "columnUse": "Field",
              "orderNumber": 2
            },
            {
              "id": 452,
              "header": "cpuPicker.quantity",
              "mappedFieldVarName": "cpuPicker.quantity",
              "columnUse": "ProductQuantity",
              "orderNumber": 3
            }
          ]
        }
      ],
      "aggregateFields": [
        {
          "type": "Number",
          "created": "2023-08-30T17:16:49.266509Z",
          "modified": "2023-08-30T17:16:49.266509Z",
          "id": 373,
          "name": "wattage Sum",
          "variableName": "cpuPicker.aggregates.wattage_sum",
          "description": null,
          "required": false,
          "category": "SET_AGGREGATE",
          "aggregateType": "SUM",
          "fieldVariableNames": [
            "cpuPicker.wattage"
          ],
          "lastModifiedBy": "scheck@cpq1.logik.dev",
          "defaultValue": null,
          "unitLabel": null,
          "precision": 32,
          "minValue": null,
          "maxValue": null,
          "stepValue": null
        }
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-product-pickers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintRelatedProductPickerResponse](#schemablueprintrelatedproductpickerresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Rules

<a id="opIdgetBlueprintRelatedRules"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/blueprints/{blueprintName}/rules`

Get Rules related to a Blueprint

<h3 id="get-related-rules-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 38,
      "name": "dateSet",
      "variableName": "dateSet",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.394634Z",
      "actionSummary": {
        "determinationAction": 1,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    },
    {
      "id": 4,
      "name": "dummy_sc",
      "variableName": "dummy_sc",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.381211Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 1,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    },
    {
      "id": 31,
      "name": "msgaboveField",
      "variableName": "msgaboveField",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.388005Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 1,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 3,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 3,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintRelatedRulesResponse](#schemablueprintrelatedrulesresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-blueprint-deployments">Blueprint > Deployments</h1>

Start and get status of Blueprint deployments

## Get Deployment History

<a id="opIdgetBlueprintDeployments"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/deployments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/deployments`

Get Blueprint Deployment History

<h3 id="get-deployment-history-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "name": "PC Builder",
      "variableName": "pCBuilder",
      "revision": 55,
      "created": "2023-09-15T17:40:53.718642Z",
      "userId": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 1,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 55,
  "totalPages": 55,
  "last": false,
  "size": 1,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-deployment-history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintDeploymentResponse](#schemablueprintdeploymentresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Deploy a Blueprint

<a id="opIdstartBlueprintDeployment"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "headers": {
    "Content-Type": "string",
    "accept": "string"
  },
  "withCredentials": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes',
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
  "headers": {
    "Content-Type": "string",
    "accept": "string"
  },
  "withCredentials": true
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v2/blueprints/{blueprintName}/runtimes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v2/blueprints/{blueprintName}/runtimes`

Start a deployment of a blueprint

> Body parameter

```json
{
  "headers": {
    "Content-Type": "string",
    "accept": "string"
  },
  "withCredentials": true
}
```

<h3 id="deploy-a-blueprint-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|body|body|object|true|none|
|» headers|body|object|false|none|
|»» Content-Type|body|string|false|none|
|»» accept|body|string|false|none|
|» withCredentials|body|boolean|false|none|

> Example responses

> 201 Response

```json
{
  "created": "2023-09-15T17:40:48.467808199Z",
  "modified": "2023-09-15T17:40:48.467808199Z",
  "id": 826,
  "jobType": "DEPLOYMENT",
  "status": "STARTED"
}
```

<h3 id="deploy-a-blueprint-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="deploy-a-blueprint-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-blueprint-export">Blueprint > Export</h1>

Export Blueprints

## Export Blueprints

<a id="opIdpostBlueprintExport"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  "string"
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export',
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
const inputBody = [
  "string"
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/blueprints/export", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/bulk/blueprints/export`

Initiate a bulk export of blueprints with the given payload.

> Body parameter

```json
[
  "string"
]
```

<h3 id="export-blueprints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[string]|true|Payload for initiating the bulk export|

> Example responses

> 200 Response

```json
{
  "created": "2019-08-24T14:15:22Z",
  "modified": "2019-08-24T14:15:22Z",
  "id": 0,
  "jobType": "string",
  "status": "string"
}
```

<h3 id="export-blueprints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bulk export job created|Inline|

<h3 id="export-blueprints-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string(date-time)|false|none|none|
|» modified|string(date-time)|false|none|none|
|» id|integer|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-blueprint-layouts">Blueprint > Layouts</h1>

Blueprint Layouts

## Get Blueprint Layouts

<a id="opIdgetBlueprintLayouts"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/layouts`

Retrieves a list of all Layouts that are associated with the Blueprint

<h3 id="get-blueprint-layouts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-blueprint-layouts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BlueprintLayoutResponse](#schemablueprintlayoutresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Layout

<a id="opIdgetLayoutByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/blueprints/{blueprintName}/layouts/{layoutName}`

<h3 id="get-a-layout-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blueprintName|path|string|true|Blueprint variable name|
|layoutName|path|string|true|Layout Variable Name|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-07T13:37:51.195021Z",
  "modified": "2023-09-07T13:37:51.195021Z",
  "id": 131,
  "label": "test",
  "variableName": "pCBuilder_test",
  "layout": {
    "version": 1,
    "label": "test",
    "variableName": "pCBuilder_test",
    "header": {
      "text": "Logik",
      "url": ""
    },
    "tierDef": [
      {
        "depth": 1,
        "representation": "VerticalTab"
      }
    ],
    "layout": {
      "label": "layoutsection",
      "variableName": "layoutsection",
      "tiers": [
        {
          "label": "Tab 1",
          "variableName": "verticaltab1",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col1",
              "elements": [
                {
                  "type": "field",
                  "variableName": "cPUType",
                  "columnOrder": 1
                },
                {
                  "type": "field",
                  "variableName": "hidden_sc",
                  "columnOrder": 1
                }
              ]
            }
          ]
        },
        {
          "label": "Tab 2",
          "variableName": "verticaltab2",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col2",
              "elements": [
                {
                  "type": "field",
                  "variableName": "textTest_swc",
                  "columnOrder": 1
                }
              ]
            }
          ]
        },
        {
          "label": "Tab 3",
          "variableName": "verticaltab3",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col3",
              "elements": [
                {
                  "type": "field",
                  "variableName": "startDate",
                  "columnOrder": 1
                },
                {
                  "type": "field",
                  "variableName": "endDate",
                  "columnOrder": 1
                }
              ]
            }
          ]
        }
      ]
    },
    "fields": [
      {
        "type": "Picklist",
        "variableName": "cPUType",
        "label": "CPU Type"
      },
      {
        "type": "Boolean",
        "variableName": "hidden_sc",
        "label": "hidden_sc"
      },
      {
        "type": "Text",
        "variableName": "textTest_swc",
        "label": "textTest_swc"
      }
    ],
    "productList": {
      "location": "modal",
      "totalLocation": "bottom",
      "hierarchyColumn": "displayName",
      "type": "sales",
      "columns": [
        {
          "variableName": "displayName",
          "label": "Product",
          "width": "40%"
        },
        {
          "variableName": "quantity",
          "label": "Qty",
          "width": "10%"
        },
        {
          "variableName": "price",
          "label": "Price",
          "width": "25%"
        }
      ],
      "displayNullPriceAs": null,
      "displayZeroPriceAs": null,
      "variableName": ""
    }
  },
  "lastModifiedBy": "scheck@cpq1.logik.dev",
  "hasLayoutFile": true
}
```

<h3 id="get-a-layout-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LayoutResponse](#schemalayoutresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-configurable-products">Configurable Products</h1>

Configurable Products

## Get List of Configurable Products

<a id="opIdgetConfigurableProducts"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts', params={
  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts?page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts?page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts?page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts?page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts?page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts',
  params: {
  'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/configurableProducts`

<h3 id="get-list-of-configurable-products-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|none|
|sort|query|string|true|none|
|size|query|number|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-06-30T18:34:18.462919Z",
      "modified": "2023-07-18T15:11:27.169540Z",
      "id": 2,
      "name": "jackson",
      "blueprintVariableName": null,
      "partnerProductId": "01t6e00000949ujAAA"
    },
    {
      "created": "2023-06-13T12:45:33.373568Z",
      "modified": "2023-06-16T17:56:45.413819Z",
      "id": 1,
      "name": "SM Parent",
      "blueprintVariableName": "psmTester",
      "partnerProductId": "01t6e0000093z9MAAQ"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 2,
  "last": true,
  "totalPages": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-configurable-products-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ConfigProductListResponse](#schemaconfigproductlistresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Configurable Product

<a id="opIdpostConfigurableProductById"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "partnerProductId": "01t6e00000949ujAAA"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts',
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
  "partnerProductId": "01t6e00000949ujAAA"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/configurableProducts`

> Body parameter

```json
{
  "partnerProductId": "01t6e00000949ujAAA"
}
```

<h3 id="get-a-configurable-product-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ConfigProductPostRequest](#schemaconfigproductpostrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
}
```

<h3 id="get-a-configurable-product-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ConfigProductPayload](#schemaconfigproductpayload)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Configurable Product

<a id="opIdputConfigurableProductById"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}',
{
  method: 'PUT',
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
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v1/configurableProducts/{configProductId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v1/configurableProducts/{configProductId}`

> Body parameter

```json
{
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
}
```

<h3 id="update-a-configurable-product-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|configProductId|path|string|true|none|
|body|body|[ConfigProductPayload](#schemaconfigproductpayload)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
}
```

<h3 id="update-a-configurable-product-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ConfigProductPayload](#schemaconfigproductpayload)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-fields">Fields</h1>

Logik Fields

## Get List of fields

<a id="opIdgetFields"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v3/fields', params={
  'area': 'USER_ONLY',  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/fields?area=USER_ONLY&page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/fields?area=USER_ONLY&page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v3/fields?area=USER_ONLY&page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v3/fields?area=USER_ONLY&page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v3/fields?area=USER_ONLY&page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v3/fields',
  params: {
  'area' => 'string',
'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v3/fields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v3/fields`

<h3 id="get-list-of-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|area|query|string|true|none|
|page|query|number|true|Page number of results to return|
|sort|query|string|true|Sort field and order of the results|
|size|query|number|true|Number of results to return|

#### Enumerated Values

|Parameter|Value|
|---|---|
|area|USER_ONLY|
|area|SYSTEM_VIEW|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 13,
      "name": "Action Context (System)",
      "variableName": "sys.actionContext",
      "description": "System Field for action context.",
      "type": "Text",
      "modified": "2023-04-21T14:27:22.469400Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 12,
      "name": "Line Id (Partner)",
      "variableName": "partner.quote.lineId",
      "description": "Unique identifier reference for the Configurable Product.",
      "type": "Text",
      "modified": "2022-10-28T16:06:05.843469Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 11,
      "name": "Currency ISO Code (Partner)",
      "variableName": "partner.quote.currencyIsoCode",
      "description": "Currency ISO Code of the Quote used to price items.",
      "type": "Text",
      "modified": "2022-09-28T13:07:47.352333Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 13,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "numberOfElements": 13,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-list-of-fields-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» type|string|true|none|none|
|»» modified|string|true|none|none|
|»» category|string|true|none|none|
|»» lastModifiedBy|string|true|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» last|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create a Field

<a id="opIdpostField"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/fields', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "type": "string",
  "name": "string",
  "variableName": "string",
  "required": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields',
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
  "type": "string",
  "name": "string",
  "variableName": "string",
  "required": true
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/fields`

> Body parameter

```json
{
  "type": "string",
  "name": "string",
  "variableName": "string",
  "required": true
}
```

<h3 id="create-a-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» type|body|string|false|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» required|body|boolean|false|none|

> Example responses

> 201 Response

```json
{
  "type": "Picklist",
  "created": "2023-09-20T14:23:52.783593669Z",
  "modified": "2023-09-20T14:23:52.783593669Z",
  "id": 72,
  "name": "newPicklist",
  "variableName": "newPicklist",
  "description": null,
  "required": false,
  "category": "USER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "single",
  "defaultValue": null
}
```

<h3 id="create-a-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-a-field-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» selectType|string|false|none|none|
|» defaultValue|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Bulk Delete Fields

<a id="opIdbulkDeleteFields"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  {
    "variableName": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete',
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
const inputBody = [
  {
    "variableName": "string"
  }
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/fields/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/bulk/fields/delete`

> Body parameter

```json
[
  {
    "variableName": "string"
  }
]
```

<h3 id="bulk-delete-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|true|none|

> Example responses

> 200 Response

```json
{
  "count": 1,
  "records": [
    {
      "num": 1,
      "success": false,
      "created": false,
      "identifier": null,
      "errorMessage": "LGK-81547D98920B422C9977D6317: Cannot delete 'test' field because it is referenced by the following blueprints: [aggTest]."
    }
  ]
}
```

<h3 id="bulk-delete-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="bulk-delete-fields-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» count|number|false|none|none|
|» records|[object]|false|none|none|
|»» num|number|false|none|none|
|»» success|boolean|false|none|none|
|»» created|boolean|false|none|none|
|»» identifier|string|false|none|none|
|»» errorMessage|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Field

<a id="opIdgetFieldByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/fields/{fieldName}`

<h3 id="get-a-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "type": "Text",
  "created": "2023-09-20T14:22:08.080151Z",
  "modified": "2023-09-20T14:22:08.080151Z",
  "id": 69,
  "name": "newText",
  "variableName": "newText",
  "description": null,
  "required": false,
  "category": "USER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "defaultValue": null,
  "minLength": null,
  "maxLength": null
}
```

<h3 id="get-a-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-a-field-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» minLength|string|false|none|none|
|» maxLength|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Field

<a id="opIdputFieldByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "type": "string",
  "created": "string",
  "modified": "string",
  "id": 0,
  "name": "string",
  "variableName": "string",
  "description": "string",
  "required": true,
  "category": "string",
  "lastModifiedBy": "string",
  "defaultValue": "string",
  "minLength": "string",
  "maxLength": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
{
  method: 'PUT',
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
  "type": "string",
  "created": "string",
  "modified": "string",
  "id": 0,
  "name": "string",
  "variableName": "string",
  "description": "string",
  "required": true,
  "category": "string",
  "lastModifiedBy": "string",
  "defaultValue": "string",
  "minLength": "string",
  "maxLength": "string"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v2/fields/{fieldName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v2/fields/{fieldName}`

> Body parameter

```json
{
  "type": "string",
  "created": "string",
  "modified": "string",
  "id": 0,
  "name": "string",
  "variableName": "string",
  "description": "string",
  "required": true,
  "category": "string",
  "lastModifiedBy": "string",
  "defaultValue": "string",
  "minLength": "string",
  "maxLength": "string"
}
```

<h3 id="update-a-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|
|body|body|object|true|none|
|» type|body|string|false|none|
|» created|body|string|false|none|
|» modified|body|string|false|none|
|» id|body|number|false|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» description|body|string|false|none|
|» required|body|boolean|false|none|
|» category|body|string|false|none|
|» lastModifiedBy|body|string|false|none|
|» defaultValue|body|string|false|none|
|» minLength|body|string|false|none|
|» maxLength|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "type": "Text",
  "created": "2023-09-20T14:22:08.080151Z",
  "modified": "2023-09-20T14:22:31.886287707Z",
  "id": 69,
  "name": "newText",
  "variableName": "newText",
  "description": null,
  "required": true,
  "category": "USER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "defaultValue": "placeholder text",
  "minLength": null,
  "maxLength": null
}
```

<h3 id="update-a-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="update-a-field-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» minLength|string|false|none|none|
|» maxLength|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-fields-picklist">Fields > Picklist</h1>

Picklist Fields

## Create Picklist Extension Data

<a id="opIdpostPicklistExtensionData"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "created": "2023-09-20T15:46:20.788140301Z",
  "modified": "2023-09-20T15:46:20.788140301Z",
  "id": 1,
  "columns": [
    {
      "created": "2023-09-20T15:46:20.807360033Z",
      "modified": "2023-09-20T15:46:20.807360033Z",
      "id": 1,
      "header": "value",
      "mappedFieldVarName": null,
      "columnUse": "Value",
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 1
    },
    {
      "created": "2023-09-20T15:46:20.864598589Z",
      "modified": "2023-09-20T15:46:20.864598589Z",
      "id": 2,
      "header": "weight",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 2
    },
    {
      "created": "2023-09-20T15:46:20.865972460Z",
      "modified": "2023-09-20T15:46:20.865972460Z",
      "id": 3,
      "header": "height",
      "mappedFieldVarName": "ProductId",
      "columnUse": "ProductId",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 3
    },
    {
      "created": "2023-09-20T15:46:20.866900305Z",
      "modified": "2023-09-20T15:46:20.866900305Z",
      "id": 4,
      "header": "ProductDescription",
      "mappedFieldVarName": "ProductDescription",
      "columnUse": "ProductDescription",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 4
    },
    {
      "created": "2023-09-20T15:46:20.867762877Z",
      "modified": "2023-09-20T15:46:20.867762877Z",
      "id": 5,
      "header": "ProductNotes",
      "mappedFieldVarName": "ProductNotes",
      "columnUse": "ProductNotes",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 5
    },
    {
      "created": "2023-09-20T15:46:20.868909161Z",
      "modified": "2023-09-20T15:46:20.868909161Z",
      "id": 6,
      "header": "ProductUniqueIdentifier",
      "mappedFieldVarName": "ProductUniqueIdentifier",
      "columnUse": "ProductUniqueIdentifier",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 6
    },
    {
      "created": "2023-09-20T15:46:20.870015484Z",
      "modified": "2023-09-20T15:46:20.870015484Z",
      "id": 7,
      "header": "ProductOrderNumber",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 7
    }
  ],
  "jobId": 101,
  "enrichEnabled": false,
  "variableName": "newPicklist"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension',
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
  "created": "2023-09-20T15:46:20.788140301Z",
  "modified": "2023-09-20T15:46:20.788140301Z",
  "id": 1,
  "columns": [
    {
      "created": "2023-09-20T15:46:20.807360033Z",
      "modified": "2023-09-20T15:46:20.807360033Z",
      "id": 1,
      "header": "value",
      "mappedFieldVarName": null,
      "columnUse": "Value",
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 1
    },
    {
      "created": "2023-09-20T15:46:20.864598589Z",
      "modified": "2023-09-20T15:46:20.864598589Z",
      "id": 2,
      "header": "weight",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 2
    },
    {
      "created": "2023-09-20T15:46:20.865972460Z",
      "modified": "2023-09-20T15:46:20.865972460Z",
      "id": 3,
      "header": "height",
      "mappedFieldVarName": "ProductId",
      "columnUse": "ProductId",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 3
    },
    {
      "created": "2023-09-20T15:46:20.866900305Z",
      "modified": "2023-09-20T15:46:20.866900305Z",
      "id": 4,
      "header": "ProductDescription",
      "mappedFieldVarName": "ProductDescription",
      "columnUse": "ProductDescription",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 4
    },
    {
      "created": "2023-09-20T15:46:20.867762877Z",
      "modified": "2023-09-20T15:46:20.867762877Z",
      "id": 5,
      "header": "ProductNotes",
      "mappedFieldVarName": "ProductNotes",
      "columnUse": "ProductNotes",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 5
    },
    {
      "created": "2023-09-20T15:46:20.868909161Z",
      "modified": "2023-09-20T15:46:20.868909161Z",
      "id": 6,
      "header": "ProductUniqueIdentifier",
      "mappedFieldVarName": "ProductUniqueIdentifier",
      "columnUse": "ProductUniqueIdentifier",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 6
    },
    {
      "created": "2023-09-20T15:46:20.870015484Z",
      "modified": "2023-09-20T15:46:20.870015484Z",
      "id": 7,
      "header": "ProductOrderNumber",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 7
    }
  ],
  "jobId": 101,
  "enrichEnabled": false,
  "variableName": "newPicklist"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/extension", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/fields/{fieldName}/extension`

> Body parameter

```json
{
  "created": "2023-09-20T15:46:20.788140301Z",
  "modified": "2023-09-20T15:46:20.788140301Z",
  "id": 1,
  "columns": [
    {
      "created": "2023-09-20T15:46:20.807360033Z",
      "modified": "2023-09-20T15:46:20.807360033Z",
      "id": 1,
      "header": "value",
      "mappedFieldVarName": null,
      "columnUse": "Value",
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 1
    },
    {
      "created": "2023-09-20T15:46:20.864598589Z",
      "modified": "2023-09-20T15:46:20.864598589Z",
      "id": 2,
      "header": "weight",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 2
    },
    {
      "created": "2023-09-20T15:46:20.865972460Z",
      "modified": "2023-09-20T15:46:20.865972460Z",
      "id": 3,
      "header": "height",
      "mappedFieldVarName": "ProductId",
      "columnUse": "ProductId",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 3
    },
    {
      "created": "2023-09-20T15:46:20.866900305Z",
      "modified": "2023-09-20T15:46:20.866900305Z",
      "id": 4,
      "header": "ProductDescription",
      "mappedFieldVarName": "ProductDescription",
      "columnUse": "ProductDescription",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 4
    },
    {
      "created": "2023-09-20T15:46:20.867762877Z",
      "modified": "2023-09-20T15:46:20.867762877Z",
      "id": 5,
      "header": "ProductNotes",
      "mappedFieldVarName": "ProductNotes",
      "columnUse": "ProductNotes",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 5
    },
    {
      "created": "2023-09-20T15:46:20.868909161Z",
      "modified": "2023-09-20T15:46:20.868909161Z",
      "id": 6,
      "header": "ProductUniqueIdentifier",
      "mappedFieldVarName": "ProductUniqueIdentifier",
      "columnUse": "ProductUniqueIdentifier",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 6
    },
    {
      "created": "2023-09-20T15:46:20.870015484Z",
      "modified": "2023-09-20T15:46:20.870015484Z",
      "id": 7,
      "header": "ProductOrderNumber",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 7
    }
  ],
  "jobId": 101,
  "enrichEnabled": false,
  "variableName": "newPicklist"
}
```

<h3 id="create-picklist-extension-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|
|body|body|[PicklistExtensionRequest](#schemapicklistextensionrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:46:20.788140Z",
  "modified": "2023-09-20T15:47:48.339646756Z",
  "id": 1,
  "columns": [
    {
      "created": "2023-09-20T15:46:20.807360Z",
      "modified": "2023-09-20T15:47:48.339697472Z",
      "id": 1,
      "header": "value",
      "mappedFieldVarName": null,
      "columnUse": "Value",
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 1
    },
    {
      "created": "2023-09-20T15:46:20.864599Z",
      "modified": "2023-09-20T15:47:48.339751892Z",
      "id": 2,
      "header": "weight",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 2
    },
    {
      "created": "2023-09-20T15:46:20.865972Z",
      "modified": "2023-09-20T15:47:48.339775139Z",
      "id": 3,
      "header": "height",
      "mappedFieldVarName": null,
      "columnUse": "ProductId",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 3
    }
  ],
  "enrichEnabled": false
}
```

<h3 id="create-picklist-extension-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-picklist-extension-data-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» columns|[object]|false|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» id|number|true|none|none|
|»» header|string|true|none|none|
|»» mappedFieldVarName|string|true|none|none|
|»» columnUse|string|true|none|none|
|»» extendedInfo|boolean|true|none|none|
|»» customKey|string|true|none|none|
|»» orderNumber|number|true|none|none|
|» enrichEnabled|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Picklist Field options

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options', params={
  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options?page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options?page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options?page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options?page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options?page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options',
  params: {
  'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/fields/{fieldName}/options`

<h3 id="get-picklist-field-options-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|Page number of results to return|
|sort|query|string|true|Sort field and order of the results|
|size|query|number|true|Number of results to return|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 37,
      "name": "option 1",
      "value": "option 1",
      "imageUrl": "",
      "description": "first option",
      "optionGroup": null,
      "modified": "2023-09-20T14:24:19.404906Z",
      "defaultValue": true,
      "order": 10
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-picklist-field-options-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-picklist-field-options-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[object]|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» value|string|false|none|none|
|»» imageUrl|string|false|none|none|
|»» description|string|false|none|none|
|»» optionGroup|string|false|none|none|
|»» modified|string|false|none|none|
|»» defaultValue|boolean|false|none|none|
|»» order|number|false|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» last|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create Picklist Field options

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  {
    "name": "string",
    "value": "string",
    "defaultValue": true,
    "imageUrl": "string",
    "description": "string",
    "order": 0,
    "optionGroup": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options',
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
const inputBody = [
  {
    "name": "string",
    "value": "string",
    "defaultValue": true,
    "imageUrl": "string",
    "description": "string",
    "order": 0,
    "optionGroup": "string"
  }
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/options", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/fields/{fieldName}/options`

> Body parameter

```json
[
  {
    "name": "string",
    "value": "string",
    "defaultValue": true,
    "imageUrl": "string",
    "description": "string",
    "order": 0,
    "optionGroup": "string"
  }
]
```

<h3 id="create-picklist-field-options-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|
|body|body|array[object]|true|none|

> Example responses

> 201 Response

```json
[
  {
    "id": 37,
    "name": "option 1",
    "value": "option 1",
    "imageUrl": "",
    "description": "first option",
    "order": 10,
    "defaultValue": true
  }
]
```

<h3 id="create-picklist-field-options-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-picklist-field-options-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» value|string|false|none|none|
|» imageUrl|string|false|none|none|
|» description|string|false|none|none|
|» order|number|false|none|none|
|» defaultValue|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-fields-related">Fields > Related</h1>

Related items for fields

## Get Related Rules

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/fields/{fieldName}/rules`

Get Rules related to a Field

<h3 id="get-related-rules-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 0,
  "last": true,
  "totalElements": 0,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 0,
  "first": true,
  "empty": true
}
```

<h3 id="get-related-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-related-rules-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[any]|false|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» last|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Blueprints

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/blueprints", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/fields/{fieldName}/blueprints`

Get Blueprints related to a Field

<h3 id="get-related-blueprints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 0,
  "last": true,
  "totalElements": 0,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 0,
  "first": true,
  "empty": true
}
```

<h3 id="get-related-blueprints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-related-blueprints-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[any]|false|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» last|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Configurable Products

<a id="opIdgetFieldRelatedConfigurableProducts"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{fieldName}/configurableProducts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/fields/{fieldName}/configurableProducts`

Get Configurable Products related to a Field

<h3 id="get-related-configurable-products-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-06-14T14:55:49.699022Z",
      "modified": "2023-06-21T22:23:09.801284Z",
      "id": 3,
      "name": "UniqueLinesConfig",
      "blueprintVariableName": "pCBuilder",
      "partnerProductId": "01t6e000009bzMuAAI"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-configurable-products-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RelatedConfigProductsResponse](#schemarelatedconfigproductsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-set">Set</h1>

Set Fields

## Get List of Sets

<a id="opIdgetSets"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/sets', params={
  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets?page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets?page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets?page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets?page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets?page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets',
  params: {
  'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/sets`

<h3 id="get-list-of-sets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|Page number of results to return|
|sort|query|string|true|Sort field and order of the results|
|size|query|number|true|Number of results to return|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 2,
      "name": "basic",
      "variableName": "basic",
      "sizeType": "setField",
      "created": "2023-08-31T18:51:49.006629Z",
      "modified": "2023-08-31T18:51:49.006629Z",
      "fields": [
        {
          "id": 3,
          "variableName": "set.basic.index",
          "name": "Index for basic",
          "description": null,
          "type": "Number",
          "distinct": false,
          "created": "2023-08-31T18:51:49.075661Z",
          "modified": "2023-08-31T18:51:49.075661Z",
          "lastModifiedBy": null
        }
      ],
      "aggregateFields": [],
      "sizeFieldVariableName": "set.basic.size",
      "sizeField": {
        "type": "Size",
        "created": "2023-08-31T18:51:49.006953Z",
        "modified": "2023-08-31T18:51:49.093582Z",
        "id": 62,
        "name": "basic Size",
        "variableName": "set.basic.size",
        "description": null,
        "required": false,
        "category": "SET_SIZE",
        "setVariableName": "basic",
        "lastModifiedBy": null,
        "defaultValue": null,
        "minValue": null,
        "maxValue": null
      },
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "id": 1,
      "name": "pickSet",
      "variableName": "pickSet",
      "sizeType": "setField",
      "created": "2023-07-24T20:05:50.031086Z",
      "modified": "2023-07-24T20:05:57.172924Z",
      "fields": [
        {
          "id": 1,
          "variableName": "set.pickSet.index",
          "name": "Index for pickSet",
          "description": null,
          "type": "Number",
          "distinct": false,
          "created": "2023-07-24T20:05:50.044686Z",
          "modified": "2023-07-24T20:05:50.044686Z",
          "lastModifiedBy": null
        },
        {
          "id": 2,
          "variableName": "psmPP",
          "name": "psmPP",
          "description": null,
          "type": "ProductPicker",
          "distinct": false,
          "created": "2023-07-24T20:05:57.170051Z",
          "modified": "2023-07-24T20:05:57.170051Z",
          "lastModifiedBy": "scheck@sm1.logik.dev"
        }
      ],
      "aggregateFields": [
        {
          "type": "Number",
          "created": "2023-07-24T20:06:27.335030Z",
          "modified": "2023-07-24T20:06:27.335030Z",
          "id": 59,
          "name": "maxQty",
          "variableName": "set.pickSet.maxQty",
          "description": null,
          "required": false,
          "category": "SET_AGGREGATE",
          "setVariableName": "pickSet",
          "aggregateType": "MAX",
          "fieldVariableNames": [
            "psmPP"
          ],
          "lastModifiedBy": "scheck@sm1.logik.dev",
          "defaultValue": null,
          "unitLabel": null,
          "precision": 32,
          "minValue": null,
          "maxValue": null,
          "stepValue": null
        }
      ],
      "sizeFieldVariableName": "set.pickSet.size",
      "sizeField": {
        "type": "Size",
        "created": "2023-07-24T20:05:50.031445Z",
        "modified": "2023-07-24T20:05:50.052828Z",
        "id": 58,
        "name": "pickSet Size",
        "variableName": "set.pickSet.size",
        "description": null,
        "required": false,
        "category": "SET_SIZE",
        "setVariableName": "pickSet",
        "lastModifiedBy": null,
        "defaultValue": null,
        "minValue": null,
        "maxValue": null
      },
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 2,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-sets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-list-of-sets-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» sizeType|string|true|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» fields|[object]|true|none|none|
|»»» id|number|true|none|none|
|»»» variableName|string|true|none|none|
|»»» name|string|true|none|none|
|»»» description|string|true|none|none|
|»»» type|string|true|none|none|
|»»» distinct|boolean|true|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» lastModifiedBy|string|true|none|none|
|»» aggregateFields|[object]|true|none|none|
|»»» type|string|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» name|string|false|none|none|
|»»» variableName|string|false|none|none|
|»»» description|string|false|none|none|
|»»» required|boolean|false|none|none|
|»»» category|string|false|none|none|
|»»» setVariableName|string|false|none|none|
|»»» aggregateType|string|false|none|none|
|»»» fieldVariableNames|[string]|false|none|none|
|»»» lastModifiedBy|string|false|none|none|
|»»» defaultValue|string|false|none|none|
|»»» unitLabel|string|false|none|none|
|»»» precision|number|false|none|none|
|»»» minValue|string|false|none|none|
|»»» maxValue|string|false|none|none|
|»»» stepValue|string|false|none|none|
|»» sizeFieldVariableName|string|true|none|none|
|»» sizeField|object|true|none|none|
|»»» type|string|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» name|string|false|none|none|
|»»» variableName|string|false|none|none|
|»»» description|string|false|none|none|
|»»» required|boolean|false|none|none|
|»»» category|string|false|none|none|
|»»» setVariableName|string|false|none|none|
|»»» lastModifiedBy|string|false|none|none|
|»»» defaultValue|string|false|none|none|
|»»» minValue|string|false|none|none|
|»»» maxValue|string|false|none|none|
|»» lastModifiedBy|string|true|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» last|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create a Set Field

<a id="opIdpostSet"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/sets', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string",
  "fields": [
    null
  ],
  "aggregateFields": [
    null
  ],
  "sizeType": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets',
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
  "name": "string",
  "variableName": "string",
  "fields": [
    null
  ],
  "aggregateFields": [
    null
  ],
  "sizeType": "string"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/sets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/sets HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/sets`

> Body parameter

```json
{
  "name": "string",
  "variableName": "string",
  "fields": [
    null
  ],
  "aggregateFields": [
    null
  ],
  "sizeType": "string"
}
```

<h3 id="create-a-set-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» fields|body|[any]|false|none|
|» aggregateFields|body|[any]|false|none|
|» sizeType|body|string|false|none|

> Example responses

> 201 Response

```json
{
  "id": 3,
  "name": "newSet",
  "variableName": "newSet",
  "sizeType": "setField",
  "created": "2023-09-20T15:25:17.300612085Z",
  "modified": "2023-09-20T15:25:17.300612085Z",
  "fields": [
    {
      "id": 4,
      "variableName": "set.newSet.index",
      "name": "Index for newSet",
      "description": null,
      "type": null,
      "distinct": false,
      "created": "2023-09-20T15:25:17.328977911Z",
      "modified": "2023-09-20T15:25:17.328977911Z",
      "lastModifiedBy": null
    }
  ],
  "aggregateFields": [],
  "sizeFieldVariableName": "set.newSet.size",
  "sizeField": {
    "type": "Size",
    "created": "2023-09-20T15:25:17.300741838Z",
    "modified": "2023-09-20T15:25:17.357986161Z",
    "id": 74,
    "name": "newSet Size",
    "variableName": "set.newSet.size",
    "description": null,
    "required": false,
    "category": "SET_SIZE",
    "setVariableName": "newSet",
    "lastModifiedBy": null,
    "defaultValue": null,
    "minValue": null,
    "maxValue": null
  },
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="create-a-set-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-a-set-field-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» sizeType|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» fields|[object]|false|none|none|
|»» id|number|false|none|none|
|»» variableName|string|false|none|none|
|»» name|string|false|none|none|
|»» description|string|false|none|none|
|»» type|string|false|none|none|
|»» distinct|boolean|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|» aggregateFields|[any]|false|none|none|
|» sizeFieldVariableName|string|false|none|none|
|» sizeField|object|false|none|none|
|»» type|string|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» required|boolean|false|none|none|
|»» category|string|false|none|none|
|»» setVariableName|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» defaultValue|string|false|none|none|
|»» minValue|string|false|none|none|
|»» maxValue|string|false|none|none|
|» lastModifiedBy|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Set Field

<a id="opIdgetSetByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/sets/{fieldName}`

<h3 id="get-a-set-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": 3,
  "name": "newSet",
  "variableName": "newSet",
  "sizeType": "setField",
  "created": "2023-09-20T15:25:17.300612Z",
  "modified": "2023-09-20T15:25:17.300612Z",
  "fields": [
    {
      "id": 4,
      "variableName": "set.newSet.index",
      "name": "Index for newSet",
      "description": null,
      "type": "Number",
      "distinct": false,
      "created": "2023-09-20T15:25:17.328978Z",
      "modified": "2023-09-20T15:25:17.328978Z",
      "lastModifiedBy": null
    }
  ],
  "aggregateFields": [],
  "sizeFieldVariableName": "set.newSet.size",
  "sizeField": {
    "type": "Size",
    "created": "2023-09-20T15:25:17.300742Z",
    "modified": "2023-09-20T15:25:17.357986Z",
    "id": 74,
    "name": "newSet Size",
    "variableName": "set.newSet.size",
    "description": null,
    "required": false,
    "category": "SET_SIZE",
    "setVariableName": "newSet",
    "lastModifiedBy": null,
    "defaultValue": null,
    "minValue": null,
    "maxValue": null
  },
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="get-a-set-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-a-set-field-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» sizeType|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» fields|[object]|false|none|none|
|»» id|number|false|none|none|
|»» variableName|string|false|none|none|
|»» name|string|false|none|none|
|»» description|string|false|none|none|
|»» type|string|false|none|none|
|»» distinct|boolean|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|» aggregateFields|[any]|false|none|none|
|» sizeFieldVariableName|string|false|none|none|
|» sizeField|object|false|none|none|
|»» type|string|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» required|boolean|false|none|none|
|»» category|string|false|none|none|
|»» setVariableName|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» defaultValue|string|false|none|none|
|»» minValue|string|false|none|none|
|»» maxValue|string|false|none|none|
|» lastModifiedBy|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Set field

<a id="opIdputSetByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string",
  "fields": [
    {
      "id": 0,
      "variableName": "string",
      "name": "string",
      "description": "string",
      "type": "string",
      "distinct": true,
      "created": "string",
      "modified": "string",
      "lastModifiedBy": "string"
    }
  ],
  "sizeType": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
{
  method: 'PUT',
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
  "name": "string",
  "variableName": "string",
  "fields": [
    {
      "id": 0,
      "variableName": "string",
      "name": "string",
      "description": "string",
      "type": "string",
      "distinct": true,
      "created": "string",
      "modified": "string",
      "lastModifiedBy": "string"
    }
  ],
  "sizeType": "string"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v1/sets/{fieldName}`

> Body parameter

```json
{
  "name": "string",
  "variableName": "string",
  "fields": [
    {
      "id": 0,
      "variableName": "string",
      "name": "string",
      "description": "string",
      "type": "string",
      "distinct": true,
      "created": "string",
      "modified": "string",
      "lastModifiedBy": "string"
    }
  ],
  "sizeType": "string"
}
```

<h3 id="update-a-set-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» fields|body|[object]|false|none|
|»» id|body|number|true|none|
|»» variableName|body|string|true|none|
|»» name|body|string|true|none|
|»» description|body|string|true|none|
|»» type|body|string|true|none|
|»» distinct|body|boolean|true|none|
|»» created|body|string|true|none|
|»» modified|body|string|true|none|
|»» lastModifiedBy|body|string|true|none|
|» sizeType|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "id": 3,
  "name": "newSet",
  "variableName": "newSet",
  "sizeType": "setField",
  "created": null,
  "modified": "2023-09-20T15:25:49.727629078Z",
  "fields": [
    {
      "id": 4,
      "variableName": "set.newSet.index",
      "name": "Index for newSet",
      "description": null,
      "type": "Number",
      "distinct": false,
      "created": "2023-09-20T15:25:17.328978Z",
      "modified": "2023-09-20T15:25:17.328978Z",
      "lastModifiedBy": null
    },
    {
      "id": 5,
      "variableName": "newNumber",
      "name": "newNumber",
      "description": null,
      "type": "Number",
      "distinct": false,
      "created": "2023-09-20T15:25:45.174439554Z",
      "modified": "2023-09-20T15:25:49.727602281Z",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "id": 6,
      "variableName": "newBoolean",
      "name": "newBoolean",
      "description": null,
      "type": "Boolean",
      "distinct": false,
      "created": "2023-09-20T15:25:49.725567275Z",
      "modified": "2023-09-20T15:25:49.725567275Z",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "aggregateFields": [],
  "sizeFieldVariableName": "set.newSet.size",
  "sizeField": {
    "type": "Size",
    "created": "2023-09-20T15:25:17.300742Z",
    "modified": "2023-09-20T15:25:17.357986Z",
    "id": 74,
    "name": "newSet Size",
    "variableName": "set.newSet.size",
    "description": null,
    "required": false,
    "category": "SET_SIZE",
    "setVariableName": "newSet",
    "lastModifiedBy": null,
    "defaultValue": null,
    "minValue": null,
    "maxValue": null
  },
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="update-a-set-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="update-a-set-field-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» sizeType|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» fields|[object]|false|none|none|
|»» id|number|true|none|none|
|»» variableName|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|true|none|none|
|»» type|string|true|none|none|
|»» distinct|boolean|true|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» lastModifiedBy|string|true|none|none|
|» aggregateFields|[any]|false|none|none|
|» sizeFieldVariableName|string|false|none|none|
|» sizeField|object|false|none|none|
|»» type|string|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» required|boolean|false|none|none|
|»» category|string|false|none|none|
|»» setVariableName|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» defaultValue|string|false|none|none|
|»» minValue|string|false|none|none|
|»» maxValue|string|false|none|none|
|» lastModifiedBy|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete a Set Field

<a id="opIddeleteSetByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/v1/sets/{fieldName}`

<h3 id="delete-a-set-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 422 Response

```json
{
  "errorCode": "LGK-4CF671086BF84DA9BFD9A14EA",
  "errorMessage": "Cannot delete array set. It is referenced in the following blueprints: newBP, pCBuilder, aggTest.",
  "timestamp": "2023-09-21T21:12:09.357521759Z"
}
```

<h3 id="delete-a-set-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|Inline|

<h3 id="delete-a-set-field-responseschema">Response Schema</h3>

Status Code **422**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» errorCode|string|false|none|none|
|» errorMessage|string|false|none|none|
|» timestamp|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Associated Fields

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/fields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/sets/{fieldName}/fields`

Get Fields associated to a Set

<h3 id="get-associated-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": 70,
    "name": "newNumber",
    "variableName": "newNumber",
    "description": null,
    "type": "Number",
    "modified": "2023-09-20T14:23:09.335027Z",
    "category": "USER",
    "lastModifiedBy": "scheck@sm1.logik.dev"
  },
  {
    "id": 71,
    "name": "newBoolean",
    "variableName": "newBoolean",
    "description": null,
    "type": "Boolean",
    "modified": "2023-09-20T14:23:37.616638Z",
    "category": "USER",
    "lastModifiedBy": "scheck@sm1.logik.dev"
  },
  {
    "id": 73,
    "name": "Index for newSet",
    "variableName": "set.newSet.index",
    "description": null,
    "type": "Number",
    "modified": "2023-09-20T15:25:17.288228Z",
    "category": "SET_INDEX",
    "lastModifiedBy": null
  }
]
```

<h3 id="get-associated-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-associated-fields-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|true|none|none|
|» name|string|true|none|none|
|» variableName|string|true|none|none|
|» description|string|true|none|none|
|» type|string|true|none|none|
|» modified|string|true|none|none|
|» category|string|true|none|none|
|» lastModifiedBy|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-set-aggregates">Set > Aggregates</h1>

Set Aggregates

## Get Aggregate Fields for a Set

<a id="opIdgetSetAggregatesByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/sets/{fieldName}/aggregateFields`

<h3 id="get-aggregate-fields-for-a-set-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "type": "Number",
    "created": "2023-09-20T15:26:28.359334Z",
    "modified": "2023-09-20T15:26:28.359334Z",
    "id": 75,
    "name": "averageAmount",
    "variableName": "set.newSet.averageAmount",
    "description": null,
    "required": false,
    "category": "SET_AGGREGATE",
    "setVariableName": "newSet",
    "aggregateType": "AVERAGE",
    "fieldVariableNames": [
      "newNumber"
    ],
    "lastModifiedBy": "scheck@sm1.logik.dev",
    "defaultValue": null,
    "unitLabel": null,
    "precision": 32,
    "minValue": null,
    "maxValue": null,
    "stepValue": null
  },
  {
    "type": "Number",
    "created": "2023-09-20T15:26:44.827942Z",
    "modified": "2023-09-20T15:26:44.827942Z",
    "id": 76,
    "name": "countBoolean",
    "variableName": "set.newSet.countBoolean",
    "description": null,
    "required": false,
    "category": "SET_AGGREGATE",
    "setVariableName": "newSet",
    "aggregateType": "COUNT",
    "fieldVariableNames": [
      "newBoolean"
    ],
    "lastModifiedBy": "scheck@sm1.logik.dev",
    "defaultValue": null,
    "unitLabel": null,
    "precision": 32,
    "minValue": null,
    "maxValue": null,
    "stepValue": null
  },
  {
    "type": "Number",
    "created": "2023-09-20T15:26:58.054905Z",
    "modified": "2023-09-20T15:26:58.054905Z",
    "id": 77,
    "name": "totalSum",
    "variableName": "set.newSet.totalSum",
    "description": null,
    "required": false,
    "category": "SET_AGGREGATE",
    "setVariableName": "newSet",
    "aggregateType": "SUM",
    "fieldVariableNames": [
      "newNumber"
    ],
    "lastModifiedBy": "scheck@sm1.logik.dev",
    "defaultValue": null,
    "unitLabel": null,
    "precision": 32,
    "minValue": null,
    "maxValue": null,
    "stepValue": null
  }
]
```

<h3 id="get-aggregate-fields-for-a-set-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-aggregate-fields-for-a-set-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|true|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» name|string|true|none|none|
|» variableName|string|true|none|none|
|» description|string|true|none|none|
|» required|boolean|true|none|none|
|» category|string|true|none|none|
|» setVariableName|string|true|none|none|
|» aggregateType|string|true|none|none|
|» fieldVariableNames|[string]|true|none|none|
|» lastModifiedBy|string|true|none|none|
|» defaultValue|string|true|none|none|
|» unitLabel|string|true|none|none|
|» precision|number|true|none|none|
|» minValue|string|true|none|none|
|» maxValue|string|true|none|none|
|» stepValue|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create an Aggregate Field on a Set

<a id="opIdpostSetAggregatesByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string",
  "aggregateType": "string",
  "type": "string",
  "fieldVariableNames": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
  "name": "string",
  "variableName": "string",
  "aggregateType": "string",
  "type": "string",
  "fieldVariableNames": [
    "string"
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/sets/{fieldName}/aggregateFields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/sets/{fieldName}/aggregateFields`

> Body parameter

```json
{
  "name": "string",
  "variableName": "string",
  "aggregateType": "string",
  "type": "string",
  "fieldVariableNames": [
    "string"
  ]
}
```

<h3 id="create-an-aggregate-field-on-a-set-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fieldName|path|string|true|none|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» aggregateType|body|string|false|none|
|» type|body|string|false|none|
|» fieldVariableNames|body|[string]|false|none|

> Example responses

> 201 Response

```json
{
  "type": "Number",
  "created": "2023-09-20T15:26:58.054905Z",
  "modified": "2023-09-20T15:26:58.054905Z",
  "id": 77,
  "name": "totalSum",
  "variableName": "set.newSet.totalSum",
  "description": null,
  "required": false,
  "category": "SET_AGGREGATE",
  "setVariableName": "newSet",
  "aggregateType": "SUM",
  "fieldVariableNames": [
    "newNumber"
  ],
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "defaultValue": null,
  "unitLabel": null,
  "precision": 32,
  "minValue": null,
  "maxValue": null,
  "stepValue": null
}
```

<h3 id="create-an-aggregate-field-on-a-set-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-an-aggregate-field-on-a-set-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» setVariableName|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-product-pickers">Product Pickers</h1>

Product Picker Fields

## Get List of Product Pickers

<a id="opIdgetProductPickers"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers', params={
  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers?page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers?page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers?page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers?page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers?page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers',
  params: {
  'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers`

<h3 id="get-list-of-product-pickers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|none|
|sort|query|string|true|none|
|size|query|number|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "string",
      "modified": "string",
      "id": 0,
      "name": "string",
      "variableName": "string",
      "description": "string",
      "required": true,
      "category": "string",
      "lastModifiedBy": "string",
      "selectType": "string",
      "enrichEnabled": true,
      "quantitySelectionLinked": true,
      "defaultType": "string",
      "defaultBomType": "string",
      "defaultParentProduct": "string",
      "defaultUom": "string",
      "defaultPricingProductSellingModelId": "string",
      "defaultPricingStartDate": "string",
      "defaultPricingEndDate": "string",
      "layoutProductDetails": [
        "string"
      ],
      "fields": [
        {
          "created": "string",
          "modified": "string",
          "id": 0,
          "variableName": "string",
          "label": "string",
          "fieldType": "string",
          "target": "string",
          "lastModifiedBy": "string"
        }
      ],
      "rules": [
        {
          "created": "string",
          "modified": "string",
          "id": 0,
          "variableName": "string",
          "type": "string",
          "status": "string",
          "columns": [
            {
              "id": 0,
              "header": "string",
              "mappedFieldVarName": "string",
              "columnUse": "string",
              "orderNumber": 0,
              "operator": "string"
            }
          ]
        }
      ],
      "aggregateFields": [
        null
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "totalPages": 0,
  "last": true,
  "totalElements": 0,
  "size": 0,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "numberOfElements": 0,
  "first": true,
  "empty": true
}
```

<h3 id="get-list-of-product-pickers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ProductPickerListResponse](#schemaproductpickerlistresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create a Product Picker Field

<a id="opIdpostProductPicker"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "type": "ProductPicker",
  "name": "newPicker",
  "variableName": "newPicker",
  "quantitySelectionLinked": false,
  "selectType": "multi",
  "fields": []
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers',
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
  "type": "ProductPicker",
  "name": "newPicker",
  "variableName": "newPicker",
  "quantitySelectionLinked": false,
  "selectType": "multi",
  "fields": []
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers`

> Body parameter

```json
{
  "type": "ProductPicker",
  "name": "newPicker",
  "variableName": "newPicker",
  "quantitySelectionLinked": false,
  "selectType": "multi",
  "fields": []
}
```

<h3 id="create-a-product-picker-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateProductPickerRequest](#schemacreateproductpickerrequest)|true|none|

> Example responses

> 201 Response

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622582782Z",
  "modified": "2023-09-20T15:55:02.622582782Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": false,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": null,
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127085Z",
      "modified": "2023-09-20T15:55:02.625127085Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673035Z",
      "modified": "2023-09-20T15:55:02.679673035Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612353Z",
      "modified": "2023-09-20T15:55:02.682612353Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [],
  "aggregateFields": null
}
```

<h3 id="create-a-product-picker-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[CreateProductPickerResponse](#schemacreateproductpickerresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Product Picker

<a id="opIdgetProductPickerByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers/{productPickerName}`

<h3 id="get-a-product-picker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:56:27.430012Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": true,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": [
    "price",
    "name"
  ],
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [
    {
      "created": "2023-09-20T15:56:44.109145Z",
      "modified": "2023-09-20T15:58:08.254303Z",
      "id": 7,
      "variableName": "newOptionInclusion",
      "type": "Inclusion",
      "status": "active",
      "columns": [
        {
          "id": 20,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 21,
          "header": "hasPromoCode",
          "mappedFieldVarName": "hasPromoCode",
          "operator": "equals",
          "columnUse": "Filter",
          "orderNumber": 1
        }
      ]
    },
    {
      "created": "2023-09-20T15:58:38.609609Z",
      "modified": "2023-09-20T15:58:38.609609Z",
      "id": 8,
      "variableName": "setFieldValues",
      "type": "Determination",
      "status": "active",
      "columns": [
        {
          "id": 22,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 23,
          "header": "newPicker.quantity",
          "mappedFieldVarName": "newPicker.quantity",
          "columnUse": "ProductQuantity",
          "orderNumber": 1
        },
        {
          "id": 24,
          "header": "newPicker.subFieldNumber",
          "mappedFieldVarName": "newPicker.subFieldNumber",
          "columnUse": "ProductExtended",
          "orderNumber": 2
        }
      ]
    },
    {
      "created": "2023-09-20T15:59:10.489882Z",
      "modified": "2023-09-20T15:59:10.489882Z",
      "id": 9,
      "variableName": "setQty",
      "type": "Quantity",
      "status": "active",
      "columns": [
        {
          "id": 25,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 26,
          "header": "quantity.min",
          "mappedFieldVarName": "quantity.min",
          "columnUse": "Field",
          "orderNumber": 1
        },
        {
          "id": 27,
          "header": "quantity.max",
          "mappedFieldVarName": "quantity.max",
          "columnUse": "Field",
          "orderNumber": 2
        },
        {
          "id": 28,
          "header": "quantity.step",
          "mappedFieldVarName": "quantity.step",
          "columnUse": "Field",
          "orderNumber": 3
        }
      ]
    }
  ],
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ]
}
```

<h3 id="get-a-product-picker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ProductPickerResponse](#schemaproductpickerresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Product Picker

<a id="opIdputProductPickerByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "id": 78,
  "name": "newPicker",
  "description": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:56:13.437274Z",
      "modified": "2023-09-20T15:56:13.437274Z",
      "id": 34,
      "variableName": "newPicker.subFieldNumber",
      "label": "subFieldNumber",
      "fieldType": "Number",
      "target": "ProductExtended",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "layoutProductDetails": [
    "name",
    "price"
  ],
  "quantitySelectionLinked": true,
  "selectType": "multi",
  "type": "ProductPicker",
  "variableName": "newPicker",
  "unsavedOptions": false,
  "unsavedAction": false,
  "savedVersion": 1,
  "rules": [],
  "currentAction": {},
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:55:55.565127Z",
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "enrichEnabled": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "options": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "aggregatesToDelete": [],
  "aggregates": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "unsavedAggregates": false
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
{
  method: 'PUT',
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
  "id": 78,
  "name": "newPicker",
  "description": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:56:13.437274Z",
      "modified": "2023-09-20T15:56:13.437274Z",
      "id": 34,
      "variableName": "newPicker.subFieldNumber",
      "label": "subFieldNumber",
      "fieldType": "Number",
      "target": "ProductExtended",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "layoutProductDetails": [
    "name",
    "price"
  ],
  "quantitySelectionLinked": true,
  "selectType": "multi",
  "type": "ProductPicker",
  "variableName": "newPicker",
  "unsavedOptions": false,
  "unsavedAction": false,
  "savedVersion": 1,
  "rules": [],
  "currentAction": {},
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:55:55.565127Z",
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "enrichEnabled": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "options": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "aggregatesToDelete": [],
  "aggregates": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "unsavedAggregates": false
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v1/productPickers/{productPickerName}`

> Body parameter

```json
{
  "id": 78,
  "name": "newPicker",
  "description": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:56:13.437274Z",
      "modified": "2023-09-20T15:56:13.437274Z",
      "id": 34,
      "variableName": "newPicker.subFieldNumber",
      "label": "subFieldNumber",
      "fieldType": "Number",
      "target": "ProductExtended",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "layoutProductDetails": [
    "name",
    "price"
  ],
  "quantitySelectionLinked": true,
  "selectType": "multi",
  "type": "ProductPicker",
  "variableName": "newPicker",
  "unsavedOptions": false,
  "unsavedAction": false,
  "savedVersion": 1,
  "rules": [],
  "currentAction": {},
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:55:55.565127Z",
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "enrichEnabled": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "options": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "aggregatesToDelete": [],
  "aggregates": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "unsavedAggregates": false
}
```

<h3 id="update-a-product-picker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|body|body|[UpdateProductPickerRequest](#schemaupdateproductpickerrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:56:27.430011623Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": true,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": [
    "price",
    "name"
  ],
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [],
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ]
}
```

<h3 id="update-a-product-picker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[UpdateProductPickerResponse](#schemaupdateproductpickerresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete a Product Picker

<a id="opIddeleteProductPickerByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/v1/productPickers/{productPickerName}`

<h3 id="delete-a-product-picker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|

> Example responses

> 422 Response

```json
{
  "errorCode": "LGK-CF4CBB2C7AD5407EAE474544B",
  "errorMessage": "Cannot delete 'proto1' field because it is referenced by the following rules: [proto1SetParentProduct].",
  "timestamp": "2023-09-21T21:10:54.734716309Z"
}
```

<h3 id="delete-a-product-picker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|Inline|

<h3 id="delete-a-product-picker-responseschema">Response Schema</h3>

Status Code **422**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» errorCode|string|false|none|none|
|» errorMessage|string|false|none|none|
|» timestamp|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-product-pickers-options">Product Pickers > Options</h1>

Product Picker Options

## Get Product Picker Options

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options', params={
  'page': '0',  'sort': 'modified%2CDESC',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options?page=0&sort=modified%2CDESC&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options?page=0&sort=modified%2CDESC&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options?page=0&sort=modified%2CDESC&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options?page=0&sort=modified%2CDESC&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options?page=0&sort=modified%2CDESC&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options',
  params: {
  'page' => 'number',
'sort' => 'string',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/fields/{productPickerName}/options`

Retrieve list of options for a Product Picker field

<h3 id="get-product-picker-options-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|none|
|sort|query|string|true|none|
|size|query|number|true|none|
|productPickerName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 3,
  "last": true,
  "totalPages": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 3,
  "first": true,
  "empty": false
}
```

<h3 id="get-product-picker-options-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ProductPickerOptionsResponse](#schemaproductpickeroptionsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create Product Picker Options

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  {
    "order": "10",
    "value": "option1",
    "defaultValue": "false",
    "name": "option1"
  },
  {
    "order": "20",
    "value": "option2",
    "defaultValue": "true",
    "name": "option2"
  },
  {
    "order": "30",
    "value": "option3",
    "defaultValue": "false",
    "name": "option3"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options',
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
const inputBody = [
  {
    "order": "10",
    "value": "option1",
    "defaultValue": "false",
    "name": "option1"
  },
  {
    "order": "20",
    "value": "option2",
    "defaultValue": "true",
    "name": "option2"
  },
  {
    "order": "30",
    "value": "option3",
    "defaultValue": "false",
    "name": "option3"
  }
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/fields/{productPickerName}/options", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/fields/{productPickerName}/options`

Add options to Product Picker

> Body parameter

```json
[
  {
    "order": "10",
    "value": "option1",
    "defaultValue": "false",
    "name": "option1"
  },
  {
    "order": "20",
    "value": "option2",
    "defaultValue": "true",
    "name": "option2"
  },
  {
    "order": "30",
    "value": "option3",
    "defaultValue": "false",
    "name": "option3"
  }
]
```

<h3 id="create-product-picker-options-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|body|body|[CreateProductPickerOptionsRequest](#schemacreateproductpickeroptionsrequest)|true|none|

> Example responses

> 201 Response

```json
[
  {
    "id": 38,
    "name": "option1",
    "value": "option1",
    "imageUrl": null,
    "description": null,
    "order": 10,
    "defaultValue": false
  },
  {
    "id": 39,
    "name": "option2",
    "value": "option2",
    "imageUrl": null,
    "description": null,
    "order": 20,
    "defaultValue": true
  },
  {
    "id": 40,
    "name": "option3",
    "value": "option3",
    "imageUrl": null,
    "description": null,
    "order": 30,
    "defaultValue": false
  }
]
```

<h3 id="create-product-picker-options-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[CreateProductPickerOptionsResponse](#schemacreateproductpickeroptionsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-product-pickers-aggregates">Product Pickers > Aggregates</h1>

Product Picker Aggregates

## Get Aggregate Fields

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers/{productPickerName}/aggregateFields`

<h3 id="get-aggregate-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "type": "Number",
    "created": "2023-09-20T15:56:22.141851Z",
    "modified": "2023-09-20T15:56:22.141851Z",
    "id": 83,
    "name": "subFieldNumber Sum",
    "variableName": "newPicker.aggregates.subFieldNumber_sum",
    "description": null,
    "required": false,
    "category": "SET_AGGREGATE",
    "aggregateType": "SUM",
    "fieldVariableNames": [
      "newPicker.subFieldNumber"
    ],
    "lastModifiedBy": "scheck@sm1.logik.dev",
    "defaultValue": null,
    "unitLabel": null,
    "precision": 32,
    "minValue": null,
    "maxValue": null,
    "stepValue": null
  }
]
```

<h3 id="get-aggregate-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-aggregate-fields-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create Aggregate Field

<a id="opIdpostProductPickerAggregate"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "fieldVariableNames": [
    "string"
  ],
  "aggregateType": "string",
  "name": "string",
  "variableName": "string",
  "type": "string",
  "isUnsaved": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
  "fieldVariableNames": [
    "string"
  ],
  "aggregateType": "string",
  "name": "string",
  "variableName": "string",
  "type": "string",
  "isUnsaved": true
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/aggregateFields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/aggregateFields`

Create a Product Picker Aggregate Field

> Body parameter

```json
{
  "fieldVariableNames": [
    "string"
  ],
  "aggregateType": "string",
  "name": "string",
  "variableName": "string",
  "type": "string",
  "isUnsaved": true
}
```

<h3 id="create-aggregate-field-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|body|body|object|true|none|
|» fieldVariableNames|body|[string]|false|none|
|» aggregateType|body|string|false|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» type|body|string|false|none|
|» isUnsaved|body|boolean|false|none|

> Example responses

> 201 Response

```json
{
  "type": "Number",
  "created": "2023-09-20T15:56:22.141850654Z",
  "modified": "2023-09-20T15:56:22.141850654Z",
  "id": 83,
  "name": "subFieldNumber Sum",
  "variableName": "newPicker.aggregates.subFieldNumber_sum",
  "description": null,
  "required": false,
  "category": "SET_AGGREGATE",
  "aggregateType": "SUM",
  "fieldVariableNames": [
    "newPicker.subFieldNumber"
  ],
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "defaultValue": null,
  "unitLabel": null,
  "precision": 32,
  "minValue": null,
  "maxValue": null,
  "stepValue": null
}
```

<h3 id="create-aggregate-field-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-aggregate-field-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-product-pickers-bulk-actions">Product Pickers > Bulk Actions</h1>

Product Picker Bulk Rules

## Import a Bulk Action

<a id="opIdimportBulkAction"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "jobType": "string",
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
  "jobType": "string",
  "file": "string"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/rules`

> Body parameter

```yaml
jobType: string
file: string

```

<h3 id="import-a-bulk-action-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|body|body|object|true|none|
|» jobType|body|string|true|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T16:00:35.614277785Z",
  "modified": "2023-09-20T16:00:35.614277785Z",
  "id": 105,
  "jobType": "PRODUCT_PICKER_RULE_IMPORT",
  "status": "STARTED"
}
```

<h3 id="import-a-bulk-action-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="import-a-bulk-action-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get List of Bulk Actions

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers/{productPickerName}/rules`

Get Bulk Actions from Product Picker

<h3 id="get-list-of-bulk-actions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-09-20T15:56:44.109145Z",
      "modified": "2023-09-20T15:58:08.254303Z",
      "id": 7,
      "variableName": "newOptionInclusion",
      "type": "Inclusion",
      "status": "active",
      "columns": [
        {
          "id": 20,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 21,
          "header": "hasPromoCode",
          "mappedFieldVarName": "hasPromoCode",
          "operator": "equals",
          "columnUse": "Filter",
          "orderNumber": 1
        }
      ]
    },
    {
      "created": "2023-09-20T16:00:35.640650Z",
      "modified": "2023-09-20T16:00:35.727075Z",
      "id": 10,
      "variableName": "setQty",
      "type": "Quantity",
      "status": "active",
      "columns": [
        {
          "id": 29,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 30,
          "header": "quantity.min",
          "mappedFieldVarName": "quantity.min",
          "columnUse": "Field",
          "orderNumber": 1
        },
        {
          "id": 31,
          "header": "quantity.max",
          "mappedFieldVarName": "quantity.max",
          "columnUse": "Field",
          "orderNumber": 2
        },
        {
          "id": 32,
          "header": "quantity.step",
          "mappedFieldVarName": "quantity.step",
          "columnUse": "Field",
          "orderNumber": 3
        }
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 20,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 2,
  "last": true,
  "totalPages": 1,
  "size": 20,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-bulk-actions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-list-of-bulk-actions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[object]|false|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» id|number|true|none|none|
|»» variableName|string|true|none|none|
|»» type|string|true|none|none|
|»» status|string|true|none|none|
|»» columns|[object]|true|none|none|
|»»» id|number|true|none|none|
|»»» header|string|true|none|none|
|»»» mappedFieldVarName|string|true|none|none|
|»»» columnUse|string|true|none|none|
|»»» orderNumber|number|true|none|none|
|»»» operator|string|false|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» last|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Bulk Action

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}`

<h3 id="get-a-bulk-action-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:56:44.109145Z",
  "modified": "2023-09-20T15:56:44.109145Z",
  "id": 7,
  "variableName": "newOptionInclusion",
  "type": "Inclusion",
  "status": "active",
  "columns": [
    {
      "id": 20,
      "header": "value",
      "mappedFieldVarName": "newPicker.value",
      "columnUse": "ProductId",
      "orderNumber": 0
    },
    {
      "id": 21,
      "header": "hasPromoCode",
      "mappedFieldVarName": "hasPromoCode",
      "operator": "equals",
      "columnUse": "Filter",
      "orderNumber": 1
    }
  ]
}
```

<h3 id="get-a-bulk-action-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-a-bulk-action-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» variableName|string|false|none|none|
|» type|string|false|none|none|
|» status|string|false|none|none|
|» columns|[object]|false|none|none|
|»» id|number|true|none|none|
|»» header|string|true|none|none|
|»» mappedFieldVarName|string|true|none|none|
|»» columnUse|string|true|none|none|
|»» orderNumber|number|true|none|none|
|»» operator|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Bulk Action

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "variableName": "string",
  "type": "string",
  "columns": [
    {
      "header": "string",
      "orderNumber": 0,
      "name": "string",
      "variableName": "string",
      "columnUse": "string",
      "operator": "string",
      "type": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
{
  method: 'PUT',
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
  "variableName": "string",
  "type": "string",
  "columns": [
    {
      "header": "string",
      "orderNumber": 0,
      "name": "string",
      "variableName": "string",
      "columnUse": "string",
      "operator": "string",
      "type": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}`

Update a Product Picker Bulk Action

> Body parameter

```json
{
  "variableName": "string",
  "type": "string",
  "columns": [
    {
      "header": "string",
      "orderNumber": 0,
      "name": "string",
      "variableName": "string",
      "columnUse": "string",
      "operator": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="update-a-bulk-action-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|
|body|body|object|true|none|
|» variableName|body|string|false|none|
|» type|body|string|false|none|
|» columns|body|[object]|false|none|
|»» header|body|string|true|none|
|»» orderNumber|body|number|true|none|
|»» name|body|string|false|none|
|»» variableName|body|string|false|none|
|»» columnUse|body|string|false|none|
|»» operator|body|string|false|none|
|»» type|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:56:44.109145Z",
  "modified": "2023-09-20T15:56:44.109145Z",
  "id": 7,
  "variableName": "newOptionInclusion",
  "type": "Inclusion",
  "status": "active",
  "columns": [
    {
      "id": 20,
      "header": "value",
      "mappedFieldVarName": "newPicker.value",
      "columnUse": "ProductId",
      "orderNumber": 0
    },
    {
      "id": 21,
      "header": "hasPromoCode",
      "mappedFieldVarName": "hasPromoCode",
      "operator": "equals",
      "columnUse": "Filter",
      "orderNumber": 1
    }
  ]
}
```

<h3 id="update-a-bulk-action-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="update-a-bulk-action-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» variableName|string|false|none|none|
|» type|string|false|none|none|
|» status|string|false|none|none|
|» columns|[object]|false|none|none|
|»» id|number|true|none|none|
|»» header|string|true|none|none|
|»» mappedFieldVarName|string|true|none|none|
|»» columnUse|string|true|none|none|
|»» orderNumber|number|true|none|none|
|»» operator|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Export a Bulk Action

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  "string"
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export',
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
const inputBody = [
  "string"
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/export", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/rules/export`

> Body parameter

```json
[
  "string"
]
```

<h3 id="export-a-bulk-action-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|body|body|array[string]|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:59:47.900704477Z",
  "modified": "2023-09-20T15:59:47.900704477Z",
  "id": 104,
  "jobType": "PRODUCT_PICKER_RULE_EXPORT",
  "status": "STARTED"
}
```

<h3 id="export-a-bulk-action-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="export-a-bulk-action-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-product-pickers-bulk-action-data">Product Pickers > Bulk Action Data</h1>

Product Picker Bulk Action Data

## Import Bulk Action Data

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "jobType": "string",
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
  "jobType": "string",
  "file": "string"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName} HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}`

Start an import job of Bulk Action Data for the specified Bulk Action.

> Body parameter

```yaml
jobType: string
file: string

```

<h3 id="import-bulk-action-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|
|body|body|object|true|none|
|» jobType|body|string|true|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:58:08.187827782Z",
  "modified": "2023-09-20T15:58:08.187827782Z",
  "id": 103,
  "jobType": "PRODUCT_PICKER_RULE_DATA_IMPORT",
  "status": "STARTED"
}
```

<h3 id="import-bulk-action-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="import-bulk-action-data-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Bulk Action Data

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows', params={
  'page': '0',  'size': '100'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows?page=0&size=100',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows?page=0&size=100',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows?page=0&size=100 \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows?page=0&size=100 HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows?page=0&size=100");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows',
  params: {
  'page' => 'number',
'size' => 'number'
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows`

<h3 id="get-bulk-action-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|none|
|size|query|number|true|none|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 1,
      "hasPromoCode": "true",
      "value": "option2"
    },
    {
      "id": 2,
      "hasPromoCode": "true",
      "value": "option3"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 2,
  "last": true,
  "totalPages": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false
}
```

<h3 id="get-bulk-action-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-bulk-action-data-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» hasPromoCode|string|true|none|none|
|»» value|string|true|none|none|
|» pageable|object|false|none|none|
|»» sort|object|false|none|none|
|»»» empty|boolean|false|none|none|
|»»» sorted|boolean|false|none|none|
|»»» unsorted|boolean|false|none|none|
|»» offset|number|false|none|none|
|»» pageNumber|number|false|none|none|
|»» pageSize|number|false|none|none|
|»» paged|boolean|false|none|none|
|»» unpaged|boolean|false|none|none|
|» totalElements|number|false|none|none|
|» last|boolean|false|none|none|
|» totalPages|number|false|none|none|
|» size|number|false|none|none|
|» number|number|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» numberOfElements|number|false|none|none|
|» first|boolean|false|none|none|
|» empty|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create Bulk Action Data

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  {
    "id": "string",
    "hasPromoCode": "string",
    "value": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows',
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
const inputBody = [
  {
    "id": "string",
    "hasPromoCode": "string",
    "value": "string"
  }
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows`

> Body parameter

```json
[
  {
    "id": "string",
    "hasPromoCode": "string",
    "value": "string"
  }
]
```

<h3 id="create-bulk-action-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|
|body|body|array[object]|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "1",
    "hasPromoCode": "true",
    "value": "option2"
  },
  {
    "id": "2",
    "hasPromoCode": "true",
    "value": "option3"
  }
]
```

<h3 id="create-bulk-action-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-bulk-action-data-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|string|true|none|none|
|» hasPromoCode|string|true|none|none|
|» value|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Export Bulk Action Data

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export',
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
const inputBody = {};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/productPickers/{productPickerName}/rules/{ruleName}/rows/export`

> Body parameter

```json
{}
```

<h3 id="export-bulk-action-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productPickerName|path|string|true|none|
|ruleName|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T15:57:33.783491724Z",
  "modified": "2023-09-20T15:57:33.783491724Z",
  "id": 102,
  "jobType": "PRODUCT_PICKER_RULE_DATA_EXPORT",
  "status": "STARTED"
}
```

<h3 id="export-bulk-action-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="export-bulk-action-data-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-rules">Rules</h1>

Logik Rules

## Get List of Rules

<a id="opIdgetRules"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v3/rules', params={
  'page': '0',  'size': '100',  'sort': 'modified%2CDESC'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules?page=0&size=100&sort=modified%2CDESC',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules?page=0&size=100&sort=modified%2CDESC',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v3/rules?page=0&size=100&sort=modified%2CDESC \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v3/rules?page=0&size=100&sort=modified%2CDESC HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v3/rules?page=0&size=100&sort=modified%2CDESC");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v3/rules',
  params: {
  'page' => 'number',
'size' => 'number',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v3/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v3/rules`

<h3 id="get-list-of-rules-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|true|Page number of results to return|
|size|query|number|true|Number of results to return|
|sort|query|string|true|Sort field and order of the results|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 54,
      "name": "addTablet",
      "variableName": "addTablet",
      "description": "",
      "status": "inactive",
      "modified": "2023-09-08T21:42:39.285656Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 1,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 55,
      "name": "add hierarchy",
      "variableName": "addHierarchy",
      "description": "",
      "status": "inactive",
      "modified": "2023-09-08T21:42:26.168890Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 1,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 53,
      "name": "calculateRAMstorage",
      "variableName": "calculateRAMstorage",
      "description": "",
      "status": "active",
      "modified": "2023-08-30T16:12:13.737755Z",
      "actionSummary": {
        "determinationAction": 1,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 45,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "numberOfElements": 45,
  "first": true,
  "empty": false
}
```

<h3 id="get-list-of-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RuleListResponse](#schemarulelistresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create a Rule

<a id="opIdpostRule"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v2/rules', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string",
  "description": "string",
  "status": "string",
  "condition": {
    "groupingType": "string"
  },
  "actions": [
    null
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules',
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
  "name": "string",
  "variableName": "string",
  "description": "string",
  "status": "string",
  "condition": {
    "groupingType": "string"
  },
  "actions": [
    null
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v2/rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v2/rules HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/rules");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v2/rules',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v2/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v2/rules`

> Body parameter

```json
{
  "name": "string",
  "variableName": "string",
  "description": "string",
  "status": "string",
  "condition": {
    "groupingType": "string"
  },
  "actions": [
    null
  ]
}
```

<h3 id="create-a-rule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» description|body|string|false|none|
|» status|body|string|false|none|
|» condition|body|object|false|none|
|»» groupingType|body|string|false|none|
|» actions|body|[any]|false|none|

> Example responses

> 201 Response

```json
{
  "created": "2023-09-20T12:13:07.272753270Z",
  "modified": "2023-09-20T12:13:07.272753270Z",
  "id": 10,
  "name": "new rule",
  "variableName": "newRule",
  "description": "basic desecription",
  "status": "active",
  "condition": {
    "groupingType": "always",
    "customLogic": null,
    "scriptId": null,
    "conditions": []
  },
  "actions": [],
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="create-a-rule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="create-a-rule-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» status|string|false|none|none|
|» condition|object|false|none|none|
|»» groupingType|string|false|none|none|
|»» customLogic|string|false|none|none|
|»» scriptId|string|false|none|none|
|»» conditions|[any]|false|none|none|
|» actions|[any]|false|none|none|
|» lastModifiedBy|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get a Rule

<a id="opIdgetRuleByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v3/rules/{ruleName}`

<h3 id="get-a-rule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T12:13:07.272753Z",
  "modified": "2023-09-20T12:13:07.272753Z",
  "id": 10,
  "name": "new rule",
  "variableName": "newRule",
  "description": "basic desecription",
  "status": "active",
  "condition": {
    "groupingType": "always",
    "customLogic": null,
    "scriptId": null,
    "conditions": []
  },
  "actions": [],
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="get-a-rule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RuleResponse](#schemaruleresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update a Rule

<a id="opIdputRuleByVariableName"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string",
  "status": "string",
  "description": "string",
  "actions": [
    {
      "type": "string",
      "created": "string",
      "modified": "string",
      "id": 0,
      "fieldVariableName": "string",
      "scriptId": "string",
      "variableName": "string",
      "visibilityType": "string",
      "message": "string",
      "messageType": "string",
      "color": "string",
      "icon": "string",
      "targetType": "string",
      "exclusionType": "string",
      "values": [
        "string"
      ],
      "behavior": "string",
      "excludedOptionDisplayBehavior": "string",
      "messageScriptId": "string",
      "optionMapping": "string",
      "setReadOnly": true,
      "overrideUserInput": true,
      "showMessage": true,
      "unionWithCurrentValue": true,
      "clearValue": true,
      "actionType": "string",
      "fieldObject": [
        null
      ],
      "products": [
        {
          "id": "string",
          "productId": "string",
          "quantity": 0,
          "bomType": "string",
          "type": "string",
          "productSellingModelId": "string",
          "startDate": "string",
          "endDate": "string",
          "orderNumber": 0,
          "uniqueIdentifier": "string",
          "price": "string",
          "description": "string",
          "notes": "string"
        }
      ]
    }
  ],
  "condition": {
    "groupingType": "string",
    "customLogic": "string",
    "scriptId": "string",
    "conditions": [
      {
        "created": "string",
        "modified": "string",
        "id": 0,
        "index": 0,
        "op": "string",
        "lhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        },
        "rhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        }
      }
    ]
  },
  "errors": {},
  "created": "string",
  "modified": "string",
  "id": 0,
  "lastModifiedBy": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
{
  method: 'PUT',
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
  "name": "string",
  "variableName": "string",
  "status": "string",
  "description": "string",
  "actions": [
    {
      "type": "string",
      "created": "string",
      "modified": "string",
      "id": 0,
      "fieldVariableName": "string",
      "scriptId": "string",
      "variableName": "string",
      "visibilityType": "string",
      "message": "string",
      "messageType": "string",
      "color": "string",
      "icon": "string",
      "targetType": "string",
      "exclusionType": "string",
      "values": [
        "string"
      ],
      "behavior": "string",
      "excludedOptionDisplayBehavior": "string",
      "messageScriptId": "string",
      "optionMapping": "string",
      "setReadOnly": true,
      "overrideUserInput": true,
      "showMessage": true,
      "unionWithCurrentValue": true,
      "clearValue": true,
      "actionType": "string",
      "fieldObject": [
        null
      ],
      "products": [
        {
          "id": "string",
          "productId": "string",
          "quantity": 0,
          "bomType": "string",
          "type": "string",
          "productSellingModelId": "string",
          "startDate": "string",
          "endDate": "string",
          "orderNumber": 0,
          "uniqueIdentifier": "string",
          "price": "string",
          "description": "string",
          "notes": "string"
        }
      ]
    }
  ],
  "condition": {
    "groupingType": "string",
    "customLogic": "string",
    "scriptId": "string",
    "conditions": [
      {
        "created": "string",
        "modified": "string",
        "id": 0,
        "index": 0,
        "op": "string",
        "lhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        },
        "rhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        }
      }
    ]
  },
  "errors": {},
  "created": "string",
  "modified": "string",
  "id": 0,
  "lastModifiedBy": "string"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/admin/v3/rules/{ruleName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/v3/rules/{ruleName}`

Use to update a Rule along with adding or removing conditions or actions

> Body parameter

```json
{
  "name": "string",
  "variableName": "string",
  "status": "string",
  "description": "string",
  "actions": [
    {
      "type": "string",
      "created": "string",
      "modified": "string",
      "id": 0,
      "fieldVariableName": "string",
      "scriptId": "string",
      "variableName": "string",
      "visibilityType": "string",
      "message": "string",
      "messageType": "string",
      "color": "string",
      "icon": "string",
      "targetType": "string",
      "exclusionType": "string",
      "values": [
        "string"
      ],
      "behavior": "string",
      "excludedOptionDisplayBehavior": "string",
      "messageScriptId": "string",
      "optionMapping": "string",
      "setReadOnly": true,
      "overrideUserInput": true,
      "showMessage": true,
      "unionWithCurrentValue": true,
      "clearValue": true,
      "actionType": "string",
      "fieldObject": [
        null
      ],
      "products": [
        {
          "id": "string",
          "productId": "string",
          "quantity": 0,
          "bomType": "string",
          "type": "string",
          "productSellingModelId": "string",
          "startDate": "string",
          "endDate": "string",
          "orderNumber": 0,
          "uniqueIdentifier": "string",
          "price": "string",
          "description": "string",
          "notes": "string"
        }
      ]
    }
  ],
  "condition": {
    "groupingType": "string",
    "customLogic": "string",
    "scriptId": "string",
    "conditions": [
      {
        "created": "string",
        "modified": "string",
        "id": 0,
        "index": 0,
        "op": "string",
        "lhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        },
        "rhs": {
          "field": true,
          "dataType": "string",
          "value": [
            "string"
          ]
        }
      }
    ]
  },
  "errors": {},
  "created": "string",
  "modified": "string",
  "id": 0,
  "lastModifiedBy": "string"
}
```

<h3 id="update-a-rule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|
|» status|body|string|false|none|
|» description|body|string|false|none|
|» actions|body|[object]|false|none|
|»» type|body|string|true|none|
|»» created|body|string|true|none|
|»» modified|body|string|true|none|
|»» id|body|number|true|none|
|»» fieldVariableName|body|string|true|none|
|»» scriptId|body|string|true|none|
|»» variableName|body|string|true|none|
|»» visibilityType|body|string|false|none|
|»» message|body|string|true|none|
|»» messageType|body|string|false|none|
|»» color|body|string|false|none|
|»» icon|body|string|false|none|
|»» targetType|body|string|false|none|
|»» exclusionType|body|string|true|none|
|»» values|body|[string]|true|none|
|»» behavior|body|string|true|none|
|»» excludedOptionDisplayBehavior|body|string|true|none|
|»» messageScriptId|body|string|true|none|
|»» optionMapping|body|string|true|none|
|»» setReadOnly|body|boolean|false|none|
|»» overrideUserInput|body|boolean|false|none|
|»» showMessage|body|boolean|false|none|
|»» unionWithCurrentValue|body|boolean|false|none|
|»» clearValue|body|boolean|false|none|
|»» actionType|body|string|false|none|
|»» fieldObject|body|[any]|false|none|
|»» products|body|[object]|false|none|
|»»» id|body|string|false|none|
|»»» productId|body|string|false|none|
|»»» quantity|body|number|false|none|
|»»» bomType|body|string|false|none|
|»»» type|body|string|false|none|
|»»» productSellingModelId|body|string|false|none|
|»»» startDate|body|string|false|none|
|»»» endDate|body|string|false|none|
|»»» orderNumber|body|number|false|none|
|»»» uniqueIdentifier|body|string|false|none|
|»»» price|body|string|false|none|
|»»» description|body|string|false|none|
|»»» notes|body|string|false|none|
|» condition|body|object|false|none|
|»» groupingType|body|string|false|none|
|»» customLogic|body|string|false|none|
|»» scriptId|body|string|false|none|
|»» conditions|body|[object]|false|none|
|»»» created|body|string|true|none|
|»»» modified|body|string|true|none|
|»»» id|body|number|true|none|
|»»» index|body|number|true|none|
|»»» op|body|string|true|none|
|»»» lhs|body|object|true|none|
|»»»» field|body|boolean|false|none|
|»»»» dataType|body|string|false|none|
|»»»» value|body|[string]|false|none|
|»»» rhs|body|object|true|none|
|»»»» field|body|boolean|false|none|
|»»»» dataType|body|string|false|none|
|»»»» value|body|[string]|false|none|
|» errors|body|object|false|none|
|» created|body|string|false|none|
|» modified|body|string|false|none|
|» id|body|number|false|none|
|» lastModifiedBy|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-20T12:13:07.272753Z",
  "modified": "2023-09-20T12:16:39.780929819Z",
  "id": 10,
  "name": "new rule",
  "variableName": "newRule",
  "description": "basic desecription",
  "status": "active",
  "condition": {
    "groupingType": "all",
    "customLogic": null,
    "scriptId": null,
    "conditions": [
      {
        "created": "2023-09-20T12:16:39.771146134Z",
        "modified": "2023-09-20T12:16:39.771146134Z",
        "id": 35,
        "index": 1,
        "op": "not equals",
        "lhs": {
          "field": true,
          "dataType": "text",
          "value": [
            "psmPP.uniqueId"
          ]
        },
        "rhs": {
          "field": false,
          "dataType": "text",
          "value": []
        }
      },
      {
        "created": "2023-09-20T12:16:39.772262565Z",
        "modified": "2023-09-20T12:16:39.772262565Z",
        "id": 36,
        "index": 2,
        "op": "contains",
        "lhs": {
          "field": true,
          "dataType": "text",
          "value": [
            "sys.productId"
          ]
        },
        "rhs": {
          "field": false,
          "dataType": "text",
          "value": [
            "01t"
          ]
        }
      }
    ]
  },
  "actions": [
    {
      "type": "Visibility",
      "created": "2023-09-20T12:14:25.713005Z",
      "modified": "2023-09-20T12:14:25.713005Z",
      "id": 6,
      "fieldVariableName": "numWidgets",
      "scriptId": null,
      "variableName": "newRule_action_1",
      "visibilityType": "hide"
    },
    {
      "type": "Message",
      "created": "2023-09-20T12:14:51.812852Z",
      "modified": "2023-09-20T12:14:51.812852Z",
      "id": 7,
      "fieldVariableName": "sys.productPrice",
      "scriptId": null,
      "variableName": "newRule_action_2",
      "message": "This is the price",
      "messageType": "info",
      "color": "#0070d2",
      "icon": "info",
      "targetType": "field"
    },
    {
      "type": "Exclusion",
      "created": "2023-09-20T12:15:14.388705Z",
      "modified": "2023-09-20T12:16:39.780976395Z",
      "id": 8,
      "fieldVariableName": "psmPP",
      "scriptId": null,
      "variableName": "newRule_action_3",
      "exclusionType": "excluded",
      "values": [
        "a"
      ],
      "behavior": "ignore",
      "excludedOptionDisplayBehavior": "hidden",
      "message": null,
      "messageScriptId": null,
      "optionMapping": null
    }
  ],
  "lastModifiedBy": "scheck@sm1.logik.dev"
}
```

<h3 id="update-a-rule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="update-a-rule-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» status|string|false|none|none|
|» condition|object|false|none|none|
|»» groupingType|string|false|none|none|
|»» customLogic|string|false|none|none|
|»» scriptId|string|false|none|none|
|»» conditions|[object]|false|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» id|number|true|none|none|
|»»» index|number|true|none|none|
|»»» op|string|true|none|none|
|»»» lhs|object|true|none|none|
|»»»» field|boolean|false|none|none|
|»»»» dataType|string|false|none|none|
|»»»» value|[string]|false|none|none|
|»»» rhs|object|true|none|none|
|»»»» field|boolean|false|none|none|
|»»»» dataType|string|false|none|none|
|»»»» value|[string]|false|none|none|
|» actions|[object]|false|none|none|
|»» type|string|true|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» id|number|true|none|none|
|»» fieldVariableName|string|true|none|none|
|»» scriptId|string|true|none|none|
|»» variableName|string|true|none|none|
|»» visibilityType|string|false|none|none|
|»» message|string|true|none|none|
|»» messageType|string|false|none|none|
|»» color|string|false|none|none|
|»» icon|string|false|none|none|
|»» targetType|string|false|none|none|
|»» exclusionType|string|false|none|none|
|»» values|[string]|false|none|none|
|»» behavior|string|false|none|none|
|»» excludedOptionDisplayBehavior|string|false|none|none|
|»» messageScriptId|string|false|none|none|
|»» optionMapping|string|false|none|none|
|» lastModifiedBy|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Bulk Delete Rules

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete', headers = headers)

print(r.json())

```

```javascript
const inputBody = '[
  {
    "variableName": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete',
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
const inputBody = [
  {
    "variableName": "string"
  }
];
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/bulk/rules/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/bulk/rules/delete`

> Body parameter

```json
[
  {
    "variableName": "string"
  }
]
```

<h3 id="bulk-delete-rules-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|true|none|

> Example responses

> 200 Response

```json
{
  "count": 1,
  "records": [
    {
      "num": 1,
      "success": true,
      "created": false,
      "identifier": "msgaboveField"
    }
  ]
}
```

<h3 id="bulk-delete-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="bulk-delete-rules-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» count|number|false|none|none|
|» records|[object]|false|none|none|
|»» num|number|false|none|none|
|»» success|boolean|false|none|none|
|»» created|boolean|false|none|none|
|»» identifier|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Clone Rule

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "variableName": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs',
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
  "name": "string",
  "variableName": "string"
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v1/rules/{ruleName}/saveAs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v1/rules/{ruleName}/saveAs`

Make a copy of the rule (from the path parameter) and related conditions and actions.

> Body parameter

```json
{
  "name": "string",
  "variableName": "string"
}
```

<h3 id="clone-rule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|
|body|body|object|true|none|
|» name|body|string|false|none|
|» variableName|body|string|false|none|

> Example responses

> 201 Response

```json
{
  "name": "advHierarchyQtyScale_2",
  "variableName": "advHierarchyQtyScale_2",
  "id": 12
}
```

<h3 id="clone-rule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h3 id="clone-rule-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» id|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-rules-related">Rules > Related</h1>

Related items for rules

## Get Related Fields

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/fields", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/rules/{ruleName}/fields`

Get Fields related to the Rule

<h3 id="get-related-fields-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 2,
      "name": "Product Id (System)",
      "variableName": "sys.productId",
      "description": "System Field for the Id of the Configured Product",
      "type": "Text",
      "modified": "2000-01-01T00:00:00Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 4,
      "name": "Product Price (System)",
      "variableName": "sys.productPrice",
      "description": "System Field for the Base Price of the Configured Product",
      "type": "Number",
      "modified": "2000-01-01T00:00:00Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 56,
      "name": "uniqueId",
      "variableName": "psmPP.uniqueId",
      "description": null,
      "type": "Text",
      "modified": "2023-07-21T17:55:30.202817Z",
      "category": "PICKER_SUBFIELD",
      "lastModifiedBy": null
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalPages": 1,
  "totalElements": 6,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 6,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-fields-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RelatedFieldsResponse](#schemarelatedfieldsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Blueprints

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/blueprints", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/rules/{ruleName}/blueprints`

Get Blueprints related to the rule

<h3 id="get-related-blueprints-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": 1,
      "name": "psmTester",
      "variableName": "psmTester",
      "description": "",
      "modified": "2023-09-08T20:54:24.225681Z",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalPages": 1,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-blueprints-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RelatedBlueprintsResponse](#schemarelatedblueprintsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Related Configurable Products

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/rules/{ruleName}/configurableProducts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/rules/{ruleName}/configurableProducts`

Get Configurable Products related to the rule

<h3 id="get-related-configurable-products-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ruleName|path|string|true|Rule Variable Name|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "created": "2023-06-14T14:55:49.699022Z",
      "modified": "2023-06-21T22:23:09.801284Z",
      "id": 3,
      "name": "UniqueLinesConfig",
      "blueprintVariableName": "pCBuilder",
      "partnerProductId": "01t6e000009bzMuAAI"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}
```

<h3 id="get-related-configurable-products-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[RelatedConfigProductsResponse](#schemarelatedconfigproductsresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-managed-tables">Managed Tables</h1>

Listing all Tables and working with indiviudal Tables

## List All Tables

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v1/managedTables`

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "dateCreated": "2023-05-30T21:19:32.650Z",
      "dateModified": "2023-05-30T21:19:55.210Z",
      "lastModifiedBy": "NO_USER_ID",
      "name": "packersTable",
      "columns": [
        {
          "name": "a",
          "type": "text",
          "description": "",
          "orderNumber": 1
        },
        {
          "name": "b",
          "type": "text",
          "description": "",
          "orderNumber": 2
        }
      ],
      "description": ""
    },
    {
      "dateCreated": "2023-05-31T02:34:32.749Z",
      "dateModified": "2023-05-31T02:34:32.749Z",
      "lastModifiedBy": "NO_USER_ID",
      "name": "shapes",
      "columns": [
        {
          "name": "sides",
          "type": "number",
          "description": "",
          "orderNumber": 1
        },
        {
          "name": "shape",
          "type": "text",
          "description": "",
          "orderNumber": 2
        }
      ],
      "description": ""
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "totalElements": 2,
  "last": true,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "first": true,
  "numberOfElements": 2,
  "empty": false
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="list-all-tables-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[ManagedTableResponse](#schemamanagedtableresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Create a new Table

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "description": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
  "name": "string",
  "description": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/managedTables/v1/managedTables`

> Body parameter

```json
{
  "name": "string",
  "description": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string"
    }
  ]
}
```

<h3 id="create-a-new-table-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagedTableCreatePayload](#schemamanagedtablecreatepayload)|false|none|

> Example responses

> 201 Response

```json
{
  "dateCreated": "string",
  "dateModified": "string",
  "lastModifiedBy": "string",
  "name": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ],
  "description": "string"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="create-a-new-table-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successful response|[ManagedTableCreateResponse](#schemamanagedtablecreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Table Data and Metadata

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v2/managedTables/{tableName}`

<h3 id="get-table-data-and-metadata-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "DATE_MODIFIED": "string",
      "DATE_CREATED": "string",
      "ID": 0,
      "additionalProperties": "string"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": true
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
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": true
  },
  "first": true,
  "numberOfElements": 0,
  "empty": true
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="get-table-data-and-metadata-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[TableResponse](#schematableresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete Table

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/managedTables/v2/managedTables/{tableName}`

<h3 id="delete-table-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|

> Example responses

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="delete-table-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Successful response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-managed-tables-metadata">Managed Tables > Metadata</h1>

Working with Table Metadata

## Get Table Metadata

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v1/managedTables/{tableName}/metadata`

<h3 id="get-table-metadata-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|

> Example responses

> 200 Response

```json
{
  "dateCreated": "string",
  "dateModified": "string",
  "lastModifiedBy": "string",
  "name": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ],
  "description": "string"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="get-table-metadata-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[ManagedTableCreateResponse](#schemamanagedtablecreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update Table Metadata

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "deleted": [
    "string"
  ],
  "added": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns',
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
  "deleted": [
    "string"
  ],
  "added": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns',
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
curl -X PATCH https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/managedTables/v1/managedTables/{tableName}/metadata/columns`

Add / Remove Table Metadata Column(s)

> Body parameter

```json
{
  "deleted": [
    "string"
  ],
  "added": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ]
}
```

<h3 id="update-table-metadata-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|body|body|[MetadataPatch](#schemametadatapatch)|false|none|

> Example responses

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="update-table-metadata-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|Successful response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete Table Metadata

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/managedTables/v1/managedTables/{tableName}/metadata/columns/{columnName}`

<h3 id="delete-table-metadata-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|columnName|path|string|true|Name of the Column in the Managed Table|

> Example responses

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="delete-table-metadata-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Successful response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-managed-tables-table-rows">Managed Tables > Table Rows</h1>

Working with individual Table Rows

## Create Table Data Row

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "rows": [
    {
      "property1": "string",
      "property2": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}',
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
  "rows": [
    {
      "property1": "string",
      "property2": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/managedTables/v1/managedTables/{tableName}`

Add new row(s) to Table

> Body parameter

```json
{
  "rows": [
    {
      "property1": "string",
      "property2": "string"
    }
  ]
}
```

<h3 id="create-table-data-row-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|body|body|object|false|none|
|» rows|body|[object]|false|none|
|»» **additionalProperties**|body|string|false|none|

> Example responses

> 201 Response

```json
{
  "rows": [
    {
      "ID": 0,
      "additionalProperties": "string"
    }
  ]
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="create-table-data-row-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successful response|[ColumnPatch](#schemacolumnpatch)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Table Data Row

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v1/managedTables/{tableName}/{rowId}`

<h3 id="get-table-data-row-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|rowId|path|integer|true|Row Id|

> Example responses

> 200 Response

```json
{
  "DATE_MODIFIED": "string",
  "DATE_CREATED": "string",
  "ID": 0,
  "additionalProperties": "string"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="get-table-data-row-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[ColumnResponse](#schemacolumnresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Update Table Data Row

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "rows": [
    {
      "ID": 0,
      "additionalProperties": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
  "rows": [
    {
      "ID": 0,
      "additionalProperties": "string"
    }
  ]
};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
curl -X PATCH https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/managedTables/v1/managedTables/{tableName}/{rowId}`

> Body parameter

```json
{
  "rows": [
    {
      "ID": 0,
      "additionalProperties": "string"
    }
  ]
}
```

<h3 id="update-table-data-row-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|rowId|path|integer|true|Row Id|
|body|body|[ColumnPatch](#schemacolumnpatch)|false|none|

> Example responses

> 200 Response

```json
{
  "ID": 0,
  "additionalProperties": "string"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="update-table-data-row-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[ColumnWithId](#schemacolumnwithid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Delete Table Data Row

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
{
  method: 'DELETE',

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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
{
  method: 'DELETE',

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
curl -X DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://{tenant}.{sector}.logik.io/api/managedTables/v1/managedTables/{tableName}/{rowId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/managedTables/v1/managedTables/{tableName}/{rowId}`

<h3 id="delete-table-data-row-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|rowId|path|integer|true|Row Id|

> Example responses

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="delete-table-data-row-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The row was deleted successfully.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-managed-tables-import">Managed Tables > Import</h1>

Import and Replace Tables

## Upload Table CSV

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "file": "string",
  "jobType": "TABLE_IMPORT"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
  "file": "string",
  "jobType": "TABLE_IMPORT"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/managedTables/v2/managedTables/{tableName}`

> Body parameter

```yaml
file: string
jobType: TABLE_IMPORT

```

<h3 id="upload-table-csv-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|body|body|object|false|none|
|» file|body|string(binary)|false|none|
|» jobType|body|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» jobType|TABLE_IMPORT|

> Example responses

> 201 Response

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="upload-table-csv-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successful response|[JobResponse](#schemajobresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Replace Table Data

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "file": "string",
  "jobType": "TABLE_IMPORT"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
{
  method: 'PUT',
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
  "file": "string",
  "jobType": "TABLE_IMPORT"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
{
  method: 'PUT',
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
curl -X PUT https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName} HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables/{tableName}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/managedTables/v2/managedTables/{tableName}`

Replace data in table with uploaded data

> Body parameter

```yaml
file: string
jobType: TABLE_IMPORT

```

<h3 id="replace-table-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|body|body|object|false|none|
|» file|body|string(binary)|false|none|
|» jobType|body|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» jobType|TABLE_IMPORT|

> Example responses

> 201 Response

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="replace-table-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successful response|[JobResponse](#schemajobresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-managed-tables-export">Managed Tables > Export</h1>

Export and Download Tables

## Export Table Data

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export',
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
const inputBody = {};
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/managedTables/v3/managedTables/{tableName}/export", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/managedTables/v3/managedTables/{tableName}/export`

Start an Export Table Data Job

> Body parameter

```json
"{}"
```

<h3 id="export-table-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tableName|path|string|true|Variable name of the Managed Table|
|body|body|object|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|body|{}|

> Example responses

> 200 Response

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="export-table-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[JobResponse](#schemajobresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Get Job Status

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v2/job/{jobId}`

Get Managed Table Job Status

<h3 id="get-job-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|jobId|path|integer|true|Job Id|

> Example responses

> 200 Response

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}
```

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="get-job-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|[JobResponse](#schemajobresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Download Table Export

> Code samples

```python
import requests
headers = {
  'Accept': 'application/octet-stream',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/octet-stream',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file',
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
  'Accept':'application/octet-stream',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file \
  -H 'Accept: application/octet-stream' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file HTTP/1.1

Accept: application/octet-stream

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file");
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
  'Accept' => 'application/octet-stream',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file',
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
        "Accept": []string{"application/octet-stream"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/job/{jobId}/file", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/managedTables/v2/job/{jobId}/file`

Download Managed Table export file from a successfully completed job.

<h3 id="download-table-export-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|jobId|path|integer|true|Job Id|

> Example responses

> 200 Response

> 400 Response

```json
{
  "errorCode": "LGK-7A407E7202264005AD03A14D9",
  "errorMessage": "Rows must not be empty.",
  "timestamp": "2023-05-31T02:08:58.235882682Z"
}
```

> 404 Response

```json
{
  "errorCode": "LGK-C2BD5E131995442CABF255BCD",
  "errorMessage": "LOGIK_OBJECT 'OBJECT_VARIABLE_NAME' was not found.",
  "timestamp": "2023-05-31T02:07:58.447433023Z"
}
```

> 5XX Response

```json
{
  "errorCode": "LGK-82DB4CF583054DF0930EDE9BE",
  "errorMessage": "An unexpected error occurred.",
  "timestamp": "2023-05-31T02:42:40.087287033Z"
}
```

<h3 id="download-table-export-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful response|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-matrix-loader">Matrix Loader</h1>

Matrix Loader import and uploads

## Import File

<a id="opIdmatrixLoaderGenericUpload"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "jobType": "GENERIC_IMPORT",
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile',
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
  "jobType": "GENERIC_IMPORT",
  "file": "string"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/admin/v2/uploadFile", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/v2/uploadFile`

A detailed description of the operation. Use markdown for rich text representation, such as **bold**, *italic*, and [links](https://swagger.io).

> Body parameter

```yaml
jobType: GENERIC_IMPORT
file: string

```

<h3 id="import-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MatrixLoaderUpload](#schemamatrixloaderupload)|true|none|

> Example responses

> 200 Response

```json
{
  "created": "2023-09-19T16:40:26.550044863Z",
  "modified": "2023-09-19T16:40:26.550044863Z",
  "id": 99,
  "jobType": "GENERIC_IMPORT",
  "status": "STARTED"
}
```

<h3 id="import-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[MatrixLoaderGenericUploadResponse](#schemamatrixloadergenericuploadresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-matrix-loader-managed-tables">Matrix Loader > Managed Tables</h1>

Matrix Loader import and uploads for Managed Tables

## Import Managed Table

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "jobType": "MANAGED_TABLES_IMPORT_UPSERT",
  "file": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables',
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
  "jobType": "MANAGED_TABLES_IMPORT_UPSERT",
  "file": "string"
};
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables',
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
curl -X POST https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables");
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
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables',
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
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://{tenant}.{sector}.logik.io/api/managedTables/v2/managedTables", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/managedTables/v2/managedTables`

Upload

> Body parameter

```yaml
jobType: MANAGED_TABLES_IMPORT_UPSERT
file: string

```

<h3 id="import-managed-table-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagedTableDataUpload](#schemamanagedtabledataupload)|true|none|

> Example responses

> 202 Response

```json
{
  "id": 1,
  "started": "2023-09-19T16:38:15.530973739Z",
  "finished": null,
  "jobType": "MANAGED_TABLES_IMPORT_UPSERT",
  "status": "STARTED"
}
```

<h3 id="import-managed-table-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|none|Inline|

<h3 id="import-managed-table-responseschema">Response Schema</h3>

Status Code **202**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|number|false|none|none|
|» started|string|false|none|none|
|» finished|string|false|none|none|
|» jobType|string|false|none|none|
|» status|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

<h1 id="logik-io-admin-api-blueprints-jobs">Jobs</h1>

Admin Job Information

## Get Admin Job Status

<a id="opIdgetAdminJobById"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}',
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
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId} HTTP/1.1

Accept: application/json

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}");
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}',
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
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v1/job/{jobId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v1/job/{jobId}`

Retrieve details of a job by providing its Id.

<h3 id="get-admin-job-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|jobId|path|integer|true|Id of the job|

> Example responses

> 200 Response

```json
{
  "id": 99,
  "started": "2023-09-19T16:40:26.554240Z",
  "finished": "2023-09-19T16:40:26.563650Z",
  "jobType": "GENERIC_IMPORT",
  "status": "COMPLETED",
  "result": {
    "success": true,
    "counts": {
      "success": 0,
      "error": 0,
      "warning": 0,
      "total": 0
    },
    "messages": []
  }
}
```

<h3 id="get-admin-job-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Admin Job Details|[AdminJobResponse](#schemaadminjobresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

## Download Bulk Export

<a id="opIddowloadJobExport"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/octet-stream',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/octet-stream',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}',
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
  'Accept':'application/octet-stream',
  'Authorization':'Bearer {access-token}'
};

fetch('https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}',
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
curl -X GET https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId} \
  -H 'Accept: application/octet-stream' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId} HTTP/1.1

Accept: application/octet-stream

```

```java
URL obj = new URL("https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}");
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
  'Accept' => 'application/octet-stream',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}',
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
        "Accept": []string{"application/octet-stream"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://{tenant}.{sector}.logik.io/api/admin/v2/bulk/export/{jobId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/v2/bulk/export/{jobId}`

Retrieve a bulk export file by providing the corresponding job Id.

<h3 id="download-bulk-export-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|jobId|path|integer|true|Id of the job|

> Example responses

> 200 Response

<h3 id="download-bulk-export-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bulk Export Result File|string|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Content-Disposition|string||Attachment filename|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
AdminApiBearerToken
</aside>

# Schemas

<h2 id="tocS_PagedResponse">PagedResponse</h2>
<!-- backwards compatibility -->
<a id="schemapagedresponse"></a>
<a id="schema_PagedResponse"></a>
<a id="tocSpagedresponse"></a>
<a id="tocspagedresponse"></a>

```json
{
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "totalPages": 0,
  "last": true,
  "totalElements": 0,
  "size": 0,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "numberOfElements": 0,
  "first": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|» offset|number|false|none|none|
|» pageNumber|number|false|none|none|
|» pageSize|number|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|number|false|none|none|
|last|boolean|false|none|none|
|totalElements|number|false|none|none|
|size|number|false|none|none|
|number|number|false|none|none|
|sort|object|false|none|none|
|» empty|boolean|false|none|none|
|» sorted|boolean|false|none|none|
|» unsorted|boolean|false|none|none|
|numberOfElements|number|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_BlueprintListResponse">BlueprintListResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintlistresponse"></a>
<a id="schema_BlueprintListResponse"></a>
<a id="tocSblueprintlistresponse"></a>
<a id="tocsblueprintlistresponse"></a>

```json
{
  "content": [
    {
      "id": 12,
      "name": "PC Builder",
      "variableName": "pCBuilder",
      "description": "",
      "modified": "2023-09-13T16:21:28.590092Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 18,
      "name": "newBP",
      "variableName": "newBP",
      "description": "ls",
      "modified": "2023-09-11T20:55:11.005400Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 8,
      "name": "ComputerBP",
      "variableName": "pickerGeneral",
      "description": "",
      "modified": "2023-09-07T13:49:40.877294Z",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 14,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 14,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» modified|string|true|none|none|
|»» lastModifiedBy|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintResponse">BlueprintResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintresponse"></a>
<a id="schema_BlueprintResponse"></a>
<a id="tocSblueprintresponse"></a>
<a id="tocsblueprintresponse"></a>

```json
{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "endDate",
    "pleExtension"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-15T17:39:47.990406Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|fields|[string]|false|none|none|
|rules|[string]|false|none|none|
|sets|[string]|false|none|none|
|layouts|[object]|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» label|string|false|none|none|
|» variableName|string|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» hasLayoutFile|boolean|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|lastModifiedBy|string|false|none|none|

<h2 id="tocS_Blueprint">Blueprint</h2>
<!-- backwards compatibility -->
<a id="schemablueprint"></a>
<a id="schema_Blueprint"></a>
<a id="tocSblueprint"></a>
<a id="tocsblueprint"></a>

```json
{
  "id": 12,
  "name": "PC Builder",
  "variableName": "pCBuilder",
  "description": "",
  "fields": [
    "cPUType",
    "textTest_swc",
    "endDate",
    "pleExtension",
    "hidden_sc",
    "startDate",
    "pricer_sc",
    "cpuPicker"
  ],
  "rules": [
    "dummy_sc",
    "dateSet",
    "msgaboveField"
  ],
  "sets": [
    "delta"
  ],
  "layouts": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "created": "2023-06-21T22:21:12.627813Z",
  "modified": "2023-09-13T16:21:28.590092Z",
  "lastModifiedBy": "scheck@cpq1.logik.dev"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|fields|[string]|false|none|none|
|rules|[string]|false|none|none|
|sets|[string]|false|none|none|
|layouts|[object]|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» label|string|false|none|none|
|» variableName|string|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» hasLayoutFile|boolean|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|lastModifiedBy|string|false|none|none|

<h2 id="tocS_BlueprintLayoutResponse">BlueprintLayoutResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintlayoutresponse"></a>
<a id="schema_BlueprintLayoutResponse"></a>
<a id="tocSblueprintlayoutresponse"></a>
<a id="tocsblueprintlayoutresponse"></a>

```json
{
  "content": [
    {
      "created": "2023-09-07T13:37:51.195021Z",
      "modified": "2023-09-07T13:37:51.195021Z",
      "id": 131,
      "label": "test",
      "variableName": "pCBuilder_test",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "hasLayoutFile": true
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» label|string|false|none|none|
|»» variableName|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» hasLayoutFile|boolean|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintRelatedSetsResponse">BlueprintRelatedSetsResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintrelatedsetsresponse"></a>
<a id="schema_BlueprintRelatedSetsResponse"></a>
<a id="tocSblueprintrelatedsetsresponse"></a>
<a id="tocsblueprintrelatedsetsresponse"></a>

```json
{
  "content": [
    {
      "id": 2,
      "name": "delta",
      "variableName": "delta",
      "sizeType": "setField",
      "created": "2023-06-07T22:34:50.052615Z",
      "modified": "2023-06-12T21:37:21.879233Z",
      "fields": [
        {
          "id": 9,
          "variableName": "textTest_swc",
          "name": "textTest_swc",
          "description": null,
          "type": "Text",
          "distinct": false,
          "created": "2023-06-12T21:37:21.877152Z",
          "modified": "2023-06-12T21:37:21.877152Z",
          "lastModifiedBy": "scheck.dev (API)"
        },
        {
          "id": 7,
          "variableName": "set.delta.index",
          "name": "Index for delta",
          "description": null,
          "type": "Number",
          "distinct": false,
          "created": "2023-06-12T21:36:46.256658Z",
          "modified": "2023-06-12T21:37:21.879317Z",
          "lastModifiedBy": null
        }
      ],
      "aggregateFields": [
        {
          "type": "Number",
          "created": "2023-06-12T21:37:11.596742Z",
          "modified": "2023-06-12T21:37:11.596742Z",
          "id": 135,
          "name": "count",
          "variableName": "set.delta.count",
          "description": null,
          "required": false,
          "category": "SET_AGGREGATE",
          "setVariableName": "delta",
          "aggregateType": "COUNT",
          "fieldVariableNames": [
            "textTest_swc"
          ],
          "lastModifiedBy": "scheck@cpq1.logik.dev",
          "defaultValue": null,
          "unitLabel": null,
          "precision": 32,
          "minValue": null,
          "maxValue": null,
          "stepValue": null
        }
      ],
      "sizeFieldVariableName": "set.delta.size",
      "sizeField": {
        "type": "Size",
        "created": "2023-06-07T22:34:50.052776Z",
        "modified": "2023-06-07T22:34:50.063657Z",
        "id": 114,
        "name": "delta Size",
        "variableName": "set.delta.size",
        "description": null,
        "required": false,
        "category": "SET_SIZE",
        "setVariableName": "delta",
        "lastModifiedBy": null,
        "defaultValue": null,
        "minValue": null,
        "maxValue": null
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» sizeType|string|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» fields|[object]|false|none|none|
|»»» id|number|true|none|none|
|»»» variableName|string|true|none|none|
|»»» name|string|true|none|none|
|»»» description|string|true|none|none|
|»»» type|string|true|none|none|
|»»» distinct|boolean|true|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» lastModifiedBy|string|true|none|none|
|»» aggregateFields|[object]|false|none|none|
|»»» type|string|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» name|string|false|none|none|
|»»» variableName|string|false|none|none|
|»»» description|string|false|none|none|
|»»» required|boolean|false|none|none|
|»»» category|string|false|none|none|
|»»» setVariableName|string|false|none|none|
|»»» aggregateType|string|false|none|none|
|»»» fieldVariableNames|[string]|false|none|none|
|»»» lastModifiedBy|string|false|none|none|
|»»» defaultValue|string|false|none|none|
|»»» unitLabel|string|false|none|none|
|»»» precision|number|false|none|none|
|»»» minValue|string|false|none|none|
|»»» maxValue|string|false|none|none|
|»»» stepValue|string|false|none|none|
|»» sizeFieldVariableName|string|false|none|none|
|»» sizeField|object|false|none|none|
|»»» type|string|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» name|string|false|none|none|
|»»» variableName|string|false|none|none|
|»»» description|string|false|none|none|
|»»» required|boolean|false|none|none|
|»»» category|string|false|none|none|
|»»» setVariableName|string|false|none|none|
|»»» lastModifiedBy|string|false|none|none|
|»»» defaultValue|string|false|none|none|
|»»» minValue|string|false|none|none|
|»»» maxValue|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_RelatedConfigProductsResponse">RelatedConfigProductsResponse</h2>
<!-- backwards compatibility -->
<a id="schemarelatedconfigproductsresponse"></a>
<a id="schema_RelatedConfigProductsResponse"></a>
<a id="tocSrelatedconfigproductsresponse"></a>
<a id="tocsrelatedconfigproductsresponse"></a>

```json
{
  "content": [
    {
      "created": "2023-06-14T14:55:49.699022Z",
      "modified": "2023-06-21T22:23:09.801284Z",
      "id": 3,
      "name": "UniqueLinesConfig",
      "blueprintVariableName": "pCBuilder",
      "partnerProductId": "01t6e000009bzMuAAI"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» created|string(date-time)|false|none|none|
|»» modified|string(date-time)|false|none|none|
|»» id|integer|false|none|none|
|»» name|string|false|none|none|
|»» blueprintVariableName|string|false|none|none|
|»» partnerProductId|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintRelatedProductPickerResponse">BlueprintRelatedProductPickerResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintrelatedproductpickerresponse"></a>
<a id="schema_BlueprintRelatedProductPickerResponse"></a>
<a id="tocSblueprintrelatedproductpickerresponse"></a>
<a id="tocsblueprintrelatedproductpickerresponse"></a>

```json
{
  "content": [
    {
      "created": "2023-06-13T21:28:17.672892Z",
      "modified": "2023-08-10T21:25:27.253738Z",
      "id": 147,
      "name": "cpuPicker",
      "variableName": "cpuPicker",
      "description": null,
      "required": false,
      "category": "PRODUCT_PICKER",
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "selectType": "single",
      "enrichEnabled": false,
      "quantitySelectionLinked": true,
      "defaultType": null,
      "defaultBomType": null,
      "defaultParentProduct": "motherboard",
      "defaultUom": null,
      "defaultPricingProductSellingModelId": null,
      "defaultPricingStartDate": null,
      "defaultPricingEndDate": null,
      "layoutProductDetails": [
        "name"
      ],
      "fields": [
        {
          "created": "2023-06-21T22:07:38.272409Z",
          "modified": "2023-06-21T22:07:38.272409Z",
          "id": 117,
          "variableName": "cpuPicker.multiThreading",
          "label": "MultiThreading",
          "fieldType": "Boolean",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-21T22:11:25.996353Z",
          "modified": "2023-06-21T22:11:25.996353Z",
          "id": 119,
          "variableName": "cpuPicker.speed",
          "label": "speed",
          "fieldType": "Picklist",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.675998Z",
          "modified": "2023-06-13T21:28:17.675998Z",
          "id": 87,
          "variableName": "cpuPicker.value",
          "label": "Value",
          "fieldType": "Text",
          "target": "ProductId",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.680095Z",
          "modified": "2023-06-13T21:28:17.680095Z",
          "id": 88,
          "variableName": "cpuPicker.select",
          "label": "Select",
          "fieldType": "Boolean",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.683457Z",
          "modified": "2023-06-13T21:28:17.683457Z",
          "id": 89,
          "variableName": "cpuPicker.quantity",
          "label": "Quantity",
          "fieldType": "Number",
          "target": "ProductQuantity",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-06-13T21:28:17.759893Z",
          "modified": "2023-06-13T21:28:17.759893Z",
          "id": 91,
          "variableName": "cpuPicker.imageUrl",
          "label": "imageUrl",
          "fieldType": "Text",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-09T15:45:24.420897Z",
          "modified": "2023-08-09T15:45:24.420897Z",
          "id": 206,
          "variableName": "cpuPicker.description",
          "label": "description",
          "fieldType": "Text",
          "target": "ProductDescription",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-09T15:45:40.624501Z",
          "modified": "2023-08-09T15:45:40.624501Z",
          "id": 207,
          "variableName": "cpuPicker.price",
          "label": "price",
          "fieldType": "Number",
          "target": "ProductPrice",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        },
        {
          "created": "2023-08-30T17:16:12.503744Z",
          "modified": "2023-08-30T17:16:12.503744Z",
          "id": 215,
          "variableName": "cpuPicker.wattage",
          "label": "wattage",
          "fieldType": "Number",
          "target": "ProductExtended",
          "lastModifiedBy": "scheck@cpq1.logik.dev"
        }
      ],
      "rules": [
        {
          "created": "2023-06-13T21:34:48.695916Z",
          "modified": "2023-06-13T21:34:48.695916Z",
          "id": 77,
          "variableName": "inclusionTest",
          "type": "Inclusion",
          "status": "active",
          "columns": [
            {
              "id": 290,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 291,
              "header": "cPUType",
              "mappedFieldVarName": "cPUType",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            }
          ]
        },
        {
          "created": "2023-08-09T15:45:54.465480Z",
          "modified": "2023-08-09T15:45:54.465480Z",
          "id": 123,
          "variableName": "setInfo",
          "type": "Determination",
          "status": "active",
          "columns": [
            {
              "id": 438,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 439,
              "header": "cpuPicker.description",
              "mappedFieldVarName": "cpuPicker.description",
              "columnUse": "ProductDescription",
              "orderNumber": 1
            },
            {
              "id": 440,
              "header": "cpuPicker.price",
              "mappedFieldVarName": "cpuPicker.price",
              "columnUse": "ProductPrice",
              "orderNumber": 2
            }
          ]
        },
        {
          "created": "2023-06-21T22:11:42.152660Z",
          "modified": "2023-06-21T22:16:31.251965Z",
          "id": 89,
          "variableName": "limitCPUs",
          "type": "Quantity",
          "status": "active",
          "columns": [
            {
              "id": 330,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 331,
              "header": "pleExtension",
              "mappedFieldVarName": "pleExtension",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            },
            {
              "id": 332,
              "header": "quantity.min",
              "mappedFieldVarName": "quantity.min",
              "columnUse": "Field",
              "orderNumber": 2
            },
            {
              "id": 333,
              "header": "quantity.max",
              "mappedFieldVarName": "quantity.max",
              "columnUse": "Field",
              "orderNumber": 3
            },
            {
              "id": 334,
              "header": "quantity.step",
              "mappedFieldVarName": "quantity.step",
              "columnUse": "Field",
              "orderNumber": 4
            }
          ]
        },
        {
          "created": "2023-08-09T15:58:50.720599Z",
          "modified": "2023-08-09T16:06:01.950247Z",
          "id": 124,
          "variableName": "predef",
          "type": "Determination",
          "message": "Action is inactive because it includes fields not associated with the current blueprint (preconfigured).",
          "status": "invalid",
          "columns": [
            {
              "id": 441,
              "header": "value",
              "mappedFieldVarName": "cpuPicker.value",
              "columnUse": "ProductId",
              "orderNumber": 0
            },
            {
              "id": 442,
              "header": "preconfigured",
              "mappedFieldVarName": "preconfigured",
              "operator": "equals",
              "columnUse": "Filter",
              "orderNumber": 1
            },
            {
              "id": 443,
              "header": "cpuPicker.select",
              "mappedFieldVarName": "cpuPicker.select",
              "columnUse": "Field",
              "orderNumber": 2
            },
            {
              "id": 452,
              "header": "cpuPicker.quantity",
              "mappedFieldVarName": "cpuPicker.quantity",
              "columnUse": "ProductQuantity",
              "orderNumber": 3
            }
          ]
        }
      ],
      "aggregateFields": [
        {
          "type": "Number",
          "created": "2023-08-30T17:16:49.266509Z",
          "modified": "2023-08-30T17:16:49.266509Z",
          "id": 373,
          "name": "wattage Sum",
          "variableName": "cpuPicker.aggregates.wattage_sum",
          "description": null,
          "required": false,
          "category": "SET_AGGREGATE",
          "aggregateType": "SUM",
          "fieldVariableNames": [
            "cpuPicker.wattage"
          ],
          "lastModifiedBy": "scheck@cpq1.logik.dev",
          "defaultValue": null,
          "unitLabel": null,
          "precision": 32,
          "minValue": null,
          "maxValue": null,
          "stepValue": null
        }
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» required|boolean|false|none|none|
|»» category|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» selectType|string|false|none|none|
|»» enrichEnabled|boolean|false|none|none|
|»» quantitySelectionLinked|boolean|false|none|none|
|»» defaultType|string|false|none|none|
|»» defaultBomType|string|false|none|none|
|»» defaultParentProduct|string|false|none|none|
|»» defaultUom|string|false|none|none|
|»» defaultPricingProductSellingModelId|string|false|none|none|
|»» defaultPricingStartDate|string|false|none|none|
|»» defaultPricingEndDate|string|false|none|none|
|»» layoutProductDetails|[string]|false|none|none|
|»» fields|[object]|false|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» id|number|true|none|none|
|»»» variableName|string|true|none|none|
|»»» label|string|true|none|none|
|»»» fieldType|string|true|none|none|
|»»» target|string|true|none|none|
|»»» lastModifiedBy|string|true|none|none|
|»» rules|[object]|false|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» id|number|true|none|none|
|»»» variableName|string|true|none|none|
|»»» type|string|true|none|none|
|»»» status|string|true|none|none|
|»»» columns|[object]|true|none|none|
|»»»» id|number|true|none|none|
|»»»» header|string|true|none|none|
|»»»» mappedFieldVarName|string|true|none|none|
|»»»» columnUse|string|true|none|none|
|»»»» orderNumber|number|true|none|none|
|»»»» operator|string|true|none|none|
|»»» message|string|false|none|none|
|»» aggregateFields|[object]|false|none|none|
|»»» type|string|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» name|string|false|none|none|
|»»» variableName|string|false|none|none|
|»»» description|string|false|none|none|
|»»» required|boolean|false|none|none|
|»»» category|string|false|none|none|
|»»» aggregateType|string|false|none|none|
|»»» fieldVariableNames|[string]|false|none|none|
|»»» lastModifiedBy|string|false|none|none|
|»»» defaultValue|string|false|none|none|
|»»» unitLabel|string|false|none|none|
|»»» precision|number|false|none|none|
|»»» minValue|string|false|none|none|
|»»» maxValue|string|false|none|none|
|»»» stepValue|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintRelatedRulesResponse">BlueprintRelatedRulesResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintrelatedrulesresponse"></a>
<a id="schema_BlueprintRelatedRulesResponse"></a>
<a id="tocSblueprintrelatedrulesresponse"></a>
<a id="tocsblueprintrelatedrulesresponse"></a>

```json
{
  "content": [
    {
      "id": 38,
      "name": "dateSet",
      "variableName": "dateSet",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.394634Z",
      "actionSummary": {
        "determinationAction": 1,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    },
    {
      "id": 4,
      "name": "dummy_sc",
      "variableName": "dummy_sc",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.381211Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 1,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    },
    {
      "id": 31,
      "name": "msgaboveField",
      "variableName": "msgaboveField",
      "description": "",
      "status": "active",
      "modified": "2023-07-19T23:47:30.388005Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 1,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck.dev (API)"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 3,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 3,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» status|string|true|none|none|
|»» modified|string|true|none|none|
|»» actionSummary|object|true|none|none|
|»»» determinationAction|number|false|none|none|
|»»» exclusionAction|number|false|none|none|
|»»» inclusionAction|number|false|none|none|
|»»» messageAction|number|false|none|none|
|»»» productAction|number|false|none|none|
|»»» visibilityAction|number|false|none|none|
|»» lastModifiedBy|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintRelatedFieldsResponse">BlueprintRelatedFieldsResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintrelatedfieldsresponse"></a>
<a id="schema_BlueprintRelatedFieldsResponse"></a>
<a id="tocSblueprintrelatedfieldsresponse"></a>
<a id="tocsblueprintrelatedfieldsresponse"></a>

```json
{
  "content": [
    {
      "type": "Picklist",
      "created": "2023-06-08T14:16:59.580802Z",
      "modified": "2023-08-09T14:29:01.175031Z",
      "id": 115,
      "name": "Motherboard Selection",
      "variableName": "pleExtension",
      "description": null,
      "required": true,
      "category": "USER",
      "hasExtension": true,
      "lastModifiedBy": "scheck@cpq1.logik.dev",
      "selectType": "single",
      "defaultValue": null
    },
    {
      "type": "Boolean",
      "created": "2023-06-02T19:01:43.730714Z",
      "modified": "2023-07-19T21:48:44.395142Z",
      "id": 91,
      "name": "hidden_sc",
      "variableName": "hidden_sc",
      "description": null,
      "required": false,
      "category": "USER",
      "lastModifiedBy": "scheck.dev (API)",
      "trueLabel": "yes",
      "falseLabel": "no",
      "defaultValue": false
    },
    {
      "type": "Picklist",
      "created": "2023-05-22T20:30:00.044552Z",
      "modified": "2023-07-19T21:48:44.353860Z",
      "id": 19,
      "name": "CPU Type",
      "variableName": "cPUType",
      "description": null,
      "required": false,
      "category": "USER",
      "lastModifiedBy": "scheck.dev (API)",
      "selectType": "single",
      "defaultValue": null
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 6,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 6,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» type|string|true|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» required|boolean|true|none|none|
|»» category|string|true|none|none|
|»» hasExtension|boolean|false|none|none|
|»» lastModifiedBy|string|true|none|none|
|»» selectType|string|true|none|none|
|»» defaultValue|string|true|none|none|
|»» trueLabel|string|false|none|none|
|»» falseLabel|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintAvailableFieldsResponse">BlueprintAvailableFieldsResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintavailablefieldsresponse"></a>
<a id="schema_BlueprintAvailableFieldsResponse"></a>
<a id="tocSblueprintavailablefieldsresponse"></a>
<a id="tocsblueprintavailablefieldsresponse"></a>

```json
{
  "content": [
    {
      "id": 303,
      "name": "jacksonFakeField10",
      "variableName": "jacksonFakeField10",
      "description": null,
      "type": "Number",
      "modified": "2023-07-11T16:32:35.498893Z",
      "category": "USER",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 323,
      "name": "FletchTestPicker2",
      "variableName": "fletchTestPicker2",
      "description": null,
      "type": "ProductPicker",
      "modified": "2023-07-17T23:00:27.861311Z",
      "category": "PRODUCT_PICKER",
      "selectType": "multi",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 281,
      "name": "jacksonPolicy",
      "variableName": "jacksonPolicy",
      "description": null,
      "type": "Picklist",
      "modified": "2023-07-05T13:47:14.613554Z",
      "category": "USER",
      "selectType": "single",
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "sorted": false,
      "unsorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 62,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": false,
    "unsorted": true
  },
  "numberOfElements": 62,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» type|string|true|none|none|
|»» modified|string|true|none|none|
|»» category|string|true|none|none|
|»» lastModifiedBy|string|true|none|none|
|»» selectType|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintDeploymentResponse">BlueprintDeploymentResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintdeploymentresponse"></a>
<a id="schema_BlueprintDeploymentResponse"></a>
<a id="tocSblueprintdeploymentresponse"></a>
<a id="tocsblueprintdeploymentresponse"></a>

```json
{
  "content": [
    {
      "name": "PC Builder",
      "variableName": "pCBuilder",
      "revision": 55,
      "created": "2023-09-15T17:40:53.718642Z",
      "userId": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 1,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 55,
  "totalPages": 55,
  "last": false,
  "size": 1,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» revision|number|false|none|none|
|»» created|string|false|none|none|
|»» userId|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_BlueprintEnrichmentScript">BlueprintEnrichmentScript</h2>
<!-- backwards compatibility -->
<a id="schemablueprintenrichmentscript"></a>
<a id="schema_BlueprintEnrichmentScript"></a>
<a id="tocSblueprintenrichmentscript"></a>
<a id="tocsblueprintenrichmentscript"></a>

```json
{
  "script": {
    "content": "var x=1;\nreturn cfgRequest;",
    "returnType": "map"
  },
  "runOnDemand": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|script|object|false|none|none|
|» content|string|false|none|none|
|» returnType|string|false|none|none|
|runOnDemand|boolean|false|none|none|

<h2 id="tocS_BlueprintScriptListResponse">BlueprintScriptListResponse</h2>
<!-- backwards compatibility -->
<a id="schemablueprintscriptlistresponse"></a>
<a id="schema_BlueprintScriptListResponse"></a>
<a id="tocSblueprintscriptlistresponse"></a>
<a id="tocsblueprintscriptlistresponse"></a>

```json
[
  {
    "created": "2023-09-15T17:40:39.187492Z",
    "modified": "2023-09-15T17:40:39.187492Z",
    "id": 9,
    "scriptArea": "INIT",
    "script": {
      "created": "2023-09-15T17:40:39.199291Z",
      "modified": "2023-09-15T17:40:39.199291Z",
      "id": 41,
      "content": "var x=1;\nreturn cfgRequest;",
      "returnType": "map"
    },
    "runOnDemand": false,
    "forcedOnDemand": false
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|scriptArea|string|false|none|none|
|script|object|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» content|string|false|none|none|
|» returnType|string|false|none|none|
|runOnDemand|boolean|false|none|none|
|forcedOnDemand|boolean|false|none|none|

<h2 id="tocS_LayoutResponse">LayoutResponse</h2>
<!-- backwards compatibility -->
<a id="schemalayoutresponse"></a>
<a id="schema_LayoutResponse"></a>
<a id="tocSlayoutresponse"></a>
<a id="tocslayoutresponse"></a>

```json
{
  "created": "2023-09-07T13:37:51.195021Z",
  "modified": "2023-09-07T13:37:51.195021Z",
  "id": 131,
  "label": "test",
  "variableName": "pCBuilder_test",
  "layout": {
    "version": 1,
    "label": "test",
    "variableName": "pCBuilder_test",
    "header": {
      "text": "Logik",
      "url": ""
    },
    "tierDef": [
      {
        "depth": 1,
        "representation": "VerticalTab"
      }
    ],
    "layout": {
      "label": "layoutsection",
      "variableName": "layoutsection",
      "tiers": [
        {
          "label": "Tab 1",
          "variableName": "verticaltab1",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col1",
              "elements": [
                {
                  "type": "field",
                  "variableName": "cPUType",
                  "columnOrder": 1
                },
                {
                  "type": "field",
                  "variableName": "hidden_sc",
                  "columnOrder": 1
                }
              ]
            }
          ]
        },
        {
          "label": "Tab 2",
          "variableName": "verticaltab2",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col2",
              "elements": [
                {
                  "type": "field",
                  "variableName": "textTest_swc",
                  "columnOrder": 1
                }
              ]
            }
          ]
        },
        {
          "label": "Tab 3",
          "variableName": "verticaltab3",
          "depth": 1,
          "columnSets": [
            {
              "variableName": "col3",
              "elements": [
                {
                  "type": "field",
                  "variableName": "startDate",
                  "columnOrder": 1
                },
                {
                  "type": "field",
                  "variableName": "endDate",
                  "columnOrder": 1
                }
              ]
            }
          ]
        }
      ]
    },
    "fields": [
      {
        "type": "Picklist",
        "variableName": "cPUType",
        "label": "CPU Type"
      },
      {
        "type": "Boolean",
        "variableName": "hidden_sc",
        "label": "hidden_sc"
      },
      {
        "type": "Text",
        "variableName": "textTest_swc",
        "label": "textTest_swc"
      }
    ],
    "productList": {
      "location": "modal",
      "totalLocation": "bottom",
      "hierarchyColumn": "displayName",
      "type": "sales",
      "columns": [
        {
          "variableName": "displayName",
          "label": "Product",
          "width": "40%"
        },
        {
          "variableName": "quantity",
          "label": "Qty",
          "width": "10%"
        },
        {
          "variableName": "price",
          "label": "Price",
          "width": "25%"
        }
      ],
      "displayNullPriceAs": null,
      "displayZeroPriceAs": null,
      "variableName": ""
    }
  },
  "lastModifiedBy": "scheck@cpq1.logik.dev",
  "hasLayoutFile": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|label|string|false|none|none|
|variableName|string|false|none|none|
|layout|object|false|none|none|
|» version|number|false|none|none|
|» label|string|false|none|none|
|» variableName|string|false|none|none|
|» header|object|false|none|none|
|»» text|string|false|none|none|
|»» url|string|false|none|none|
|» tierDef|[object]|false|none|none|
|»» depth|number|false|none|none|
|»» representation|string|false|none|none|
|» layout|object|false|none|none|
|»» label|string|false|none|none|
|»» variableName|string|false|none|none|
|»» tiers|[object]|false|none|none|
|»»» label|string|true|none|none|
|»»» variableName|string|true|none|none|
|»»» depth|number|true|none|none|
|»»» columnSets|[object]|true|none|none|
|»»»» variableName|string|true|none|none|
|»»»» elements|[object]|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» variableName|string|true|none|none|
|»»»»» columnOrder|number|true|none|none|
|» fields|[object]|false|none|none|
|»» type|string|true|none|none|
|»» variableName|string|true|none|none|
|»» label|string|true|none|none|
|» productList|object|false|none|none|
|»» location|string|false|none|none|
|»» totalLocation|string|false|none|none|
|»» hierarchyColumn|string|false|none|none|
|»» type|string|false|none|none|
|»» columns|[object]|false|none|none|
|»»» variableName|string|true|none|none|
|»»» label|string|true|none|none|
|»»» width|string|true|none|none|
|»» displayNullPriceAs|string|false|none|none|
|»» displayZeroPriceAs|string|false|none|none|
|»» variableName|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|hasLayoutFile|boolean|false|none|none|

<h2 id="tocS_ConfigProductPostRequest">ConfigProductPostRequest</h2>
<!-- backwards compatibility -->
<a id="schemaconfigproductpostrequest"></a>
<a id="schema_ConfigProductPostRequest"></a>
<a id="tocSconfigproductpostrequest"></a>
<a id="tocsconfigproductpostrequest"></a>

```json
{
  "partnerProductId": "01t6e00000949ujAAA"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|partnerProductId|string|false|none|none|

<h2 id="tocS_ConfigProductPayload">ConfigProductPayload</h2>
<!-- backwards compatibility -->
<a id="schemaconfigproductpayload"></a>
<a id="schema_ConfigProductPayload"></a>
<a id="tocSconfigproductpayload"></a>
<a id="tocsconfigproductpayload"></a>

```json
{
  "created": "2023-06-30T18:34:18.462919Z",
  "modified": "2023-09-20T17:01:23.129051Z",
  "id": 2,
  "name": "jackson",
  "blueprintVariableName": null,
  "partnerProductId": "01t6e00000949ujAAA"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string(date-time)|false|none|none|
|modified|string(date-time)|false|none|none|
|id|integer|false|none|none|
|name|string|false|none|none|
|blueprintVariableName|string|false|none|none|
|partnerProductId|string|false|none|none|

<h2 id="tocS_ConfigProductListResponse">ConfigProductListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaconfigproductlistresponse"></a>
<a id="schema_ConfigProductListResponse"></a>
<a id="tocSconfigproductlistresponse"></a>
<a id="tocsconfigproductlistresponse"></a>

```json
{
  "content": [
    {
      "created": "2023-06-30T18:34:18.462919Z",
      "modified": "2023-07-18T15:11:27.169540Z",
      "id": 2,
      "name": "jackson",
      "blueprintVariableName": null,
      "partnerProductId": "01t6e00000949ujAAA"
    },
    {
      "created": "2023-06-13T12:45:33.373568Z",
      "modified": "2023-06-16T17:56:45.413819Z",
      "id": 1,
      "name": "SM Parent",
      "blueprintVariableName": "psmTester",
      "partnerProductId": "01t6e0000093z9MAAQ"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 2,
  "last": true,
  "totalPages": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» created|string|true|none|none|
|»» modified|string|true|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» blueprintVariableName|string|true|none|none|
|»» partnerProductId|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_PicklistExtensionRequest">PicklistExtensionRequest</h2>
<!-- backwards compatibility -->
<a id="schemapicklistextensionrequest"></a>
<a id="schema_PicklistExtensionRequest"></a>
<a id="tocSpicklistextensionrequest"></a>
<a id="tocspicklistextensionrequest"></a>

```json
{
  "created": "2023-09-20T15:46:20.788140301Z",
  "modified": "2023-09-20T15:46:20.788140301Z",
  "id": 1,
  "columns": [
    {
      "created": "2023-09-20T15:46:20.807360033Z",
      "modified": "2023-09-20T15:46:20.807360033Z",
      "id": 1,
      "header": "value",
      "mappedFieldVarName": null,
      "columnUse": "Value",
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 1
    },
    {
      "created": "2023-09-20T15:46:20.864598589Z",
      "modified": "2023-09-20T15:46:20.864598589Z",
      "id": 2,
      "header": "weight",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 2
    },
    {
      "created": "2023-09-20T15:46:20.865972460Z",
      "modified": "2023-09-20T15:46:20.865972460Z",
      "id": 3,
      "header": "height",
      "mappedFieldVarName": "ProductId",
      "columnUse": "ProductId",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 3
    },
    {
      "created": "2023-09-20T15:46:20.866900305Z",
      "modified": "2023-09-20T15:46:20.866900305Z",
      "id": 4,
      "header": "ProductDescription",
      "mappedFieldVarName": "ProductDescription",
      "columnUse": "ProductDescription",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 4
    },
    {
      "created": "2023-09-20T15:46:20.867762877Z",
      "modified": "2023-09-20T15:46:20.867762877Z",
      "id": 5,
      "header": "ProductNotes",
      "mappedFieldVarName": "ProductNotes",
      "columnUse": "ProductNotes",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 5
    },
    {
      "created": "2023-09-20T15:46:20.868909161Z",
      "modified": "2023-09-20T15:46:20.868909161Z",
      "id": 6,
      "header": "ProductUniqueIdentifier",
      "mappedFieldVarName": "ProductUniqueIdentifier",
      "columnUse": "ProductUniqueIdentifier",
      "extendedInfo": true,
      "customKey": null,
      "orderNumber": 6
    },
    {
      "created": "2023-09-20T15:46:20.870015484Z",
      "modified": "2023-09-20T15:46:20.870015484Z",
      "id": 7,
      "header": "ProductOrderNumber",
      "mappedFieldVarName": null,
      "columnUse": null,
      "extendedInfo": false,
      "customKey": null,
      "orderNumber": 7
    }
  ],
  "jobId": 101,
  "enrichEnabled": false,
  "variableName": "newPicklist"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|columns|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» header|string|true|none|none|
|» mappedFieldVarName|string|true|none|none|
|» columnUse|string|true|none|none|
|» extendedInfo|boolean|true|none|none|
|» customKey|string|true|none|none|
|» orderNumber|number|true|none|none|
|jobId|number|false|none|none|
|enrichEnabled|boolean|false|none|none|
|variableName|string|false|none|none|

<h2 id="tocS_ProductPickerListResponse">ProductPickerListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductpickerlistresponse"></a>
<a id="schema_ProductPickerListResponse"></a>
<a id="tocSproductpickerlistresponse"></a>
<a id="tocsproductpickerlistresponse"></a>

```json
{
  "content": [
    {
      "created": "string",
      "modified": "string",
      "id": 0,
      "name": "string",
      "variableName": "string",
      "description": "string",
      "required": true,
      "category": "string",
      "lastModifiedBy": "string",
      "selectType": "string",
      "enrichEnabled": true,
      "quantitySelectionLinked": true,
      "defaultType": "string",
      "defaultBomType": "string",
      "defaultParentProduct": "string",
      "defaultUom": "string",
      "defaultPricingProductSellingModelId": "string",
      "defaultPricingStartDate": "string",
      "defaultPricingEndDate": "string",
      "layoutProductDetails": [
        "string"
      ],
      "fields": [
        {
          "created": "string",
          "modified": "string",
          "id": 0,
          "variableName": "string",
          "label": "string",
          "fieldType": "string",
          "target": "string",
          "lastModifiedBy": "string"
        }
      ],
      "rules": [
        {
          "created": "string",
          "modified": "string",
          "id": 0,
          "variableName": "string",
          "type": "string",
          "status": "string",
          "columns": [
            {
              "id": 0,
              "header": "string",
              "mappedFieldVarName": "string",
              "columnUse": "string",
              "orderNumber": 0,
              "operator": "string"
            }
          ]
        }
      ],
      "aggregateFields": [
        null
      ]
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "totalPages": 0,
  "last": true,
  "totalElements": 0,
  "size": 0,
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "numberOfElements": 0,
  "first": true,
  "empty": true
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» created|string|false|none|none|
|»» modified|string|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» required|boolean|false|none|none|
|»» category|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|
|»» selectType|string|false|none|none|
|»» enrichEnabled|boolean|false|none|none|
|»» quantitySelectionLinked|boolean|false|none|none|
|»» defaultType|string|false|none|none|
|»» defaultBomType|string|false|none|none|
|»» defaultParentProduct|string|false|none|none|
|»» defaultUom|string|false|none|none|
|»» defaultPricingProductSellingModelId|string|false|none|none|
|»» defaultPricingStartDate|string|false|none|none|
|»» defaultPricingEndDate|string|false|none|none|
|»» layoutProductDetails|[string]|false|none|none|
|»» fields|[object]|false|none|none|
|»»» created|string|true|none|none|
|»»» modified|string|true|none|none|
|»»» id|number|true|none|none|
|»»» variableName|string|true|none|none|
|»»» label|string|true|none|none|
|»»» fieldType|string|true|none|none|
|»»» target|string|true|none|none|
|»»» lastModifiedBy|string|true|none|none|
|»» rules|[object]|false|none|none|
|»»» created|string|false|none|none|
|»»» modified|string|false|none|none|
|»»» id|number|false|none|none|
|»»» variableName|string|false|none|none|
|»»» type|string|false|none|none|
|»»» status|string|false|none|none|
|»»» columns|[object]|false|none|none|
|»»»» id|number|true|none|none|
|»»»» header|string|true|none|none|
|»»»» mappedFieldVarName|string|true|none|none|
|»»»» columnUse|string|true|none|none|
|»»»» orderNumber|number|true|none|none|
|»»»» operator|string|false|none|none|
|»» aggregateFields|[any]|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_CreateProductPickerRequest">CreateProductPickerRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreateproductpickerrequest"></a>
<a id="schema_CreateProductPickerRequest"></a>
<a id="tocScreateproductpickerrequest"></a>
<a id="tocscreateproductpickerrequest"></a>

```json
{
  "type": "ProductPicker",
  "name": "newPicker",
  "variableName": "newPicker",
  "quantitySelectionLinked": false,
  "selectType": "multi",
  "fields": []
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|quantitySelectionLinked|boolean|false|none|none|
|selectType|string|false|none|none|
|fields|[any]|false|none|none|

<h2 id="tocS_CreateProductPickerResponse">CreateProductPickerResponse</h2>
<!-- backwards compatibility -->
<a id="schemacreateproductpickerresponse"></a>
<a id="schema_CreateProductPickerResponse"></a>
<a id="tocScreateproductpickerresponse"></a>
<a id="tocscreateproductpickerresponse"></a>

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622582782Z",
  "modified": "2023-09-20T15:55:02.622582782Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": false,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": null,
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127085Z",
      "modified": "2023-09-20T15:55:02.625127085Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673035Z",
      "modified": "2023-09-20T15:55:02.679673035Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612353Z",
      "modified": "2023-09-20T15:55:02.682612353Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [],
  "aggregateFields": null
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|required|boolean|false|none|none|
|category|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|selectType|string|false|none|none|
|enrichEnabled|boolean|false|none|none|
|quantitySelectionLinked|boolean|false|none|none|
|defaultType|string|false|none|none|
|defaultBomType|string|false|none|none|
|defaultParentProduct|string|false|none|none|
|defaultUom|string|false|none|none|
|defaultPricingProductSellingModelId|string|false|none|none|
|defaultPricingStartDate|string|false|none|none|
|defaultPricingEndDate|string|false|none|none|
|layoutProductDetails|string|false|none|none|
|fields|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» variableName|string|true|none|none|
|» label|string|true|none|none|
|» fieldType|string|true|none|none|
|» target|string|true|none|none|
|» lastModifiedBy|string|true|none|none|
|rules|[any]|false|none|none|
|aggregateFields|string|false|none|none|

<h2 id="tocS_UpdateProductPickerRequest">UpdateProductPickerRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateproductpickerrequest"></a>
<a id="schema_UpdateProductPickerRequest"></a>
<a id="tocSupdateproductpickerrequest"></a>
<a id="tocsupdateproductpickerrequest"></a>

```json
{
  "id": 78,
  "name": "newPicker",
  "description": null,
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:56:13.437274Z",
      "modified": "2023-09-20T15:56:13.437274Z",
      "id": 34,
      "variableName": "newPicker.subFieldNumber",
      "label": "subFieldNumber",
      "fieldType": "Number",
      "target": "ProductExtended",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "layoutProductDetails": [
    "name",
    "price"
  ],
  "quantitySelectionLinked": true,
  "selectType": "multi",
  "type": "ProductPicker",
  "variableName": "newPicker",
  "unsavedOptions": false,
  "unsavedAction": false,
  "savedVersion": 1,
  "rules": [],
  "currentAction": {},
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:55:55.565127Z",
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "enrichEnabled": false,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "options": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "aggregatesToDelete": [],
  "aggregates": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ],
  "unsavedAggregates": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|name|string|false|none|none|
|description|string|false|none|none|
|fields|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» variableName|string|true|none|none|
|» label|string|true|none|none|
|» fieldType|string|true|none|none|
|» target|string|true|none|none|
|» lastModifiedBy|string|true|none|none|
|layoutProductDetails|[string]|false|none|none|
|quantitySelectionLinked|boolean|false|none|none|
|selectType|string|false|none|none|
|type|string|false|none|none|
|variableName|string|false|none|none|
|unsavedOptions|boolean|false|none|none|
|unsavedAction|boolean|false|none|none|
|savedVersion|number|false|none|none|
|rules|[any]|false|none|none|
|currentAction|object|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|required|boolean|false|none|none|
|category|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|enrichEnabled|boolean|false|none|none|
|defaultType|string|false|none|none|
|defaultBomType|string|false|none|none|
|defaultParentProduct|string|false|none|none|
|defaultUom|string|false|none|none|
|defaultPricingProductSellingModelId|string|false|none|none|
|defaultPricingStartDate|string|false|none|none|
|defaultPricingEndDate|string|false|none|none|
|aggregateFields|[object]|false|none|none|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|
|options|[object]|false|none|none|
|» id|number|true|none|none|
|» name|string|true|none|none|
|» value|string|true|none|none|
|» imageUrl|string|true|none|none|
|» description|string|true|none|none|
|» optionGroup|string|true|none|none|
|» modified|string|true|none|none|
|» defaultValue|boolean|true|none|none|
|» order|number|true|none|none|
|aggregatesToDelete|[any]|false|none|none|
|aggregates|[object]|false|none|none|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|
|unsavedAggregates|boolean|false|none|none|

<h2 id="tocS_UpdateProductPickerResponse">UpdateProductPickerResponse</h2>
<!-- backwards compatibility -->
<a id="schemaupdateproductpickerresponse"></a>
<a id="schema_UpdateProductPickerResponse"></a>
<a id="tocSupdateproductpickerresponse"></a>
<a id="tocsupdateproductpickerresponse"></a>

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:56:27.430011623Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": true,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": [
    "price",
    "name"
  ],
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [],
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|required|boolean|false|none|none|
|category|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|selectType|string|false|none|none|
|enrichEnabled|boolean|false|none|none|
|quantitySelectionLinked|boolean|false|none|none|
|defaultType|string|false|none|none|
|defaultBomType|string|false|none|none|
|defaultParentProduct|string|false|none|none|
|defaultUom|string|false|none|none|
|defaultPricingProductSellingModelId|string|false|none|none|
|defaultPricingStartDate|string|false|none|none|
|defaultPricingEndDate|string|false|none|none|
|layoutProductDetails|[string]|false|none|none|
|fields|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» variableName|string|true|none|none|
|» label|string|true|none|none|
|» fieldType|string|true|none|none|
|» target|string|true|none|none|
|» lastModifiedBy|string|true|none|none|
|rules|[any]|false|none|none|
|aggregateFields|[object]|false|none|none|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|

<h2 id="tocS_ProductPickerOptionsResponse">ProductPickerOptionsResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductpickeroptionsresponse"></a>
<a id="schema_ProductPickerOptionsResponse"></a>
<a id="tocSproductpickeroptionsresponse"></a>
<a id="tocsproductpickeroptionsresponse"></a>

```json
{
  "content": [
    {
      "id": 38,
      "name": "option1",
      "value": "option1",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.907745Z",
      "defaultValue": false,
      "order": 10
    },
    {
      "id": 39,
      "name": "option2",
      "value": "option2",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.917641Z",
      "defaultValue": true,
      "order": 20
    },
    {
      "id": 40,
      "name": "option3",
      "value": "option3",
      "imageUrl": null,
      "description": null,
      "optionGroup": null,
      "modified": "2023-09-20T15:55:28.922805Z",
      "defaultValue": false,
      "order": 30
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalElements": 3,
  "last": true,
  "totalPages": 1,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 3,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» value|string|true|none|none|
|»» imageUrl|string|true|none|none|
|»» description|string|true|none|none|
|»» optionGroup|string|true|none|none|
|»» modified|string|true|none|none|
|»» defaultValue|boolean|true|none|none|
|»» order|number|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_CreateProductPickerOptionsRequest">CreateProductPickerOptionsRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreateproductpickeroptionsrequest"></a>
<a id="schema_CreateProductPickerOptionsRequest"></a>
<a id="tocScreateproductpickeroptionsrequest"></a>
<a id="tocscreateproductpickeroptionsrequest"></a>

```json
[
  {
    "order": "10",
    "value": "option1",
    "defaultValue": "false",
    "name": "option1"
  },
  {
    "order": "20",
    "value": "option2",
    "defaultValue": "true",
    "name": "option2"
  },
  {
    "order": "30",
    "value": "option3",
    "defaultValue": "false",
    "name": "option3"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|order|string|true|none|none|
|value|string|true|none|none|
|defaultValue|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_CreateProductPickerOptionsResponse">CreateProductPickerOptionsResponse</h2>
<!-- backwards compatibility -->
<a id="schemacreateproductpickeroptionsresponse"></a>
<a id="schema_CreateProductPickerOptionsResponse"></a>
<a id="tocScreateproductpickeroptionsresponse"></a>
<a id="tocscreateproductpickeroptionsresponse"></a>

```json
[
  {
    "id": 38,
    "name": "option1",
    "value": "option1",
    "imageUrl": null,
    "description": null,
    "order": 10,
    "defaultValue": false
  },
  {
    "id": 39,
    "name": "option2",
    "value": "option2",
    "imageUrl": null,
    "description": null,
    "order": 20,
    "defaultValue": true
  },
  {
    "id": 40,
    "name": "option3",
    "value": "option3",
    "imageUrl": null,
    "description": null,
    "order": 30,
    "defaultValue": false
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|true|none|none|
|name|string|true|none|none|
|value|string|true|none|none|
|imageUrl|string|true|none|none|
|description|string|true|none|none|
|order|number|true|none|none|
|defaultValue|boolean|true|none|none|

<h2 id="tocS_ProductPickerResponse">ProductPickerResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductpickerresponse"></a>
<a id="schema_ProductPickerResponse"></a>
<a id="tocSproductpickerresponse"></a>
<a id="tocsproductpickerresponse"></a>

```json
{
  "type": "ProductPicker",
  "created": "2023-09-20T15:55:02.622583Z",
  "modified": "2023-09-20T15:56:27.430012Z",
  "id": 78,
  "name": "newPicker",
  "variableName": "newPicker",
  "description": null,
  "required": true,
  "category": "PRODUCT_PICKER",
  "lastModifiedBy": "scheck@sm1.logik.dev",
  "selectType": "multi",
  "enrichEnabled": false,
  "quantitySelectionLinked": true,
  "defaultType": null,
  "defaultBomType": null,
  "defaultParentProduct": null,
  "defaultUom": null,
  "defaultPricingProductSellingModelId": "OneTime_OneTime_2023_07_05",
  "defaultPricingStartDate": null,
  "defaultPricingEndDate": null,
  "layoutProductDetails": [
    "price",
    "name"
  ],
  "fields": [
    {
      "created": "2023-09-20T15:55:02.625127Z",
      "modified": "2023-09-20T15:55:02.625127Z",
      "id": 31,
      "variableName": "newPicker.value",
      "label": "Value",
      "fieldType": "Text",
      "target": "ProductId",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.679673Z",
      "modified": "2023-09-20T15:55:02.679673Z",
      "id": 32,
      "variableName": "newPicker.select",
      "label": "Select",
      "fieldType": "Boolean",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    },
    {
      "created": "2023-09-20T15:55:02.682612Z",
      "modified": "2023-09-20T15:55:02.682612Z",
      "id": 33,
      "variableName": "newPicker.quantity",
      "label": "Quantity",
      "fieldType": "Number",
      "target": "ProductQuantity",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "rules": [
    {
      "created": "2023-09-20T15:56:44.109145Z",
      "modified": "2023-09-20T15:58:08.254303Z",
      "id": 7,
      "variableName": "newOptionInclusion",
      "type": "Inclusion",
      "status": "active",
      "columns": [
        {
          "id": 20,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 21,
          "header": "hasPromoCode",
          "mappedFieldVarName": "hasPromoCode",
          "operator": "equals",
          "columnUse": "Filter",
          "orderNumber": 1
        }
      ]
    },
    {
      "created": "2023-09-20T15:58:38.609609Z",
      "modified": "2023-09-20T15:58:38.609609Z",
      "id": 8,
      "variableName": "setFieldValues",
      "type": "Determination",
      "status": "active",
      "columns": [
        {
          "id": 22,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 23,
          "header": "newPicker.quantity",
          "mappedFieldVarName": "newPicker.quantity",
          "columnUse": "ProductQuantity",
          "orderNumber": 1
        },
        {
          "id": 24,
          "header": "newPicker.subFieldNumber",
          "mappedFieldVarName": "newPicker.subFieldNumber",
          "columnUse": "ProductExtended",
          "orderNumber": 2
        }
      ]
    },
    {
      "created": "2023-09-20T15:59:10.489882Z",
      "modified": "2023-09-20T15:59:10.489882Z",
      "id": 9,
      "variableName": "setQty",
      "type": "Quantity",
      "status": "active",
      "columns": [
        {
          "id": 25,
          "header": "value",
          "mappedFieldVarName": "newPicker.value",
          "columnUse": "ProductId",
          "orderNumber": 0
        },
        {
          "id": 26,
          "header": "quantity.min",
          "mappedFieldVarName": "quantity.min",
          "columnUse": "Field",
          "orderNumber": 1
        },
        {
          "id": 27,
          "header": "quantity.max",
          "mappedFieldVarName": "quantity.max",
          "columnUse": "Field",
          "orderNumber": 2
        },
        {
          "id": 28,
          "header": "quantity.step",
          "mappedFieldVarName": "quantity.step",
          "columnUse": "Field",
          "orderNumber": 3
        }
      ]
    }
  ],
  "aggregateFields": [
    {
      "type": "Number",
      "created": "2023-09-20T15:56:22.141851Z",
      "modified": "2023-09-20T15:56:22.141851Z",
      "id": 83,
      "name": "subFieldNumber Sum",
      "variableName": "newPicker.aggregates.subFieldNumber_sum",
      "description": null,
      "required": false,
      "category": "SET_AGGREGATE",
      "aggregateType": "SUM",
      "fieldVariableNames": [
        "newPicker.subFieldNumber"
      ],
      "lastModifiedBy": "scheck@sm1.logik.dev",
      "defaultValue": null,
      "unitLabel": null,
      "precision": 32,
      "minValue": null,
      "maxValue": null,
      "stepValue": null
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|required|boolean|false|none|none|
|category|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|selectType|string|false|none|none|
|enrichEnabled|boolean|false|none|none|
|quantitySelectionLinked|boolean|false|none|none|
|defaultType|string|false|none|none|
|defaultBomType|string|false|none|none|
|defaultParentProduct|string|false|none|none|
|defaultUom|string|false|none|none|
|defaultPricingProductSellingModelId|string|false|none|none|
|defaultPricingStartDate|string|false|none|none|
|defaultPricingEndDate|string|false|none|none|
|layoutProductDetails|[string]|false|none|none|
|fields|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» variableName|string|true|none|none|
|» label|string|true|none|none|
|» fieldType|string|true|none|none|
|» target|string|true|none|none|
|» lastModifiedBy|string|true|none|none|
|rules|[object]|false|none|none|
|» created|string|true|none|none|
|» modified|string|true|none|none|
|» id|number|true|none|none|
|» variableName|string|true|none|none|
|» type|string|true|none|none|
|» status|string|true|none|none|
|» columns|[object]|true|none|none|
|»» id|number|true|none|none|
|»» header|string|true|none|none|
|»» mappedFieldVarName|string|true|none|none|
|»» columnUse|string|true|none|none|
|»» orderNumber|number|true|none|none|
|»» operator|string|false|none|none|
|aggregateFields|[object]|false|none|none|
|» type|string|false|none|none|
|» created|string|false|none|none|
|» modified|string|false|none|none|
|» id|number|false|none|none|
|» name|string|false|none|none|
|» variableName|string|false|none|none|
|» description|string|false|none|none|
|» required|boolean|false|none|none|
|» category|string|false|none|none|
|» aggregateType|string|false|none|none|
|» fieldVariableNames|[string]|false|none|none|
|» lastModifiedBy|string|false|none|none|
|» defaultValue|string|false|none|none|
|» unitLabel|string|false|none|none|
|» precision|number|false|none|none|
|» minValue|string|false|none|none|
|» maxValue|string|false|none|none|
|» stepValue|string|false|none|none|

<h2 id="tocS_RuleListResponse">RuleListResponse</h2>
<!-- backwards compatibility -->
<a id="schemarulelistresponse"></a>
<a id="schema_RuleListResponse"></a>
<a id="tocSrulelistresponse"></a>
<a id="tocsrulelistresponse"></a>

```json
{
  "content": [
    {
      "id": 54,
      "name": "addTablet",
      "variableName": "addTablet",
      "description": "",
      "status": "inactive",
      "modified": "2023-09-08T21:42:39.285656Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 1,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 55,
      "name": "add hierarchy",
      "variableName": "addHierarchy",
      "description": "",
      "status": "inactive",
      "modified": "2023-09-08T21:42:26.168890Z",
      "actionSummary": {
        "determinationAction": 0,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 1,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    },
    {
      "id": 53,
      "name": "calculateRAMstorage",
      "variableName": "calculateRAMstorage",
      "description": "",
      "status": "active",
      "modified": "2023-08-30T16:12:13.737755Z",
      "actionSummary": {
        "determinationAction": 1,
        "exclusionAction": 0,
        "inclusionAction": 0,
        "messageAction": 0,
        "productAction": 0,
        "visibilityAction": 0
      },
      "lastModifiedBy": "scheck@cpq1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "last": true,
  "totalElements": 45,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "numberOfElements": 45,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» status|string|true|none|none|
|»» modified|string|true|none|none|
|»» actionSummary|object|true|none|none|
|»»» determinationAction|number|false|none|none|
|»»» exclusionAction|number|false|none|none|
|»»» inclusionAction|number|false|none|none|
|»»» messageAction|number|false|none|none|
|»»» productAction|number|false|none|none|
|»»» visibilityAction|number|false|none|none|
|»» lastModifiedBy|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_RuleResponse">RuleResponse</h2>
<!-- backwards compatibility -->
<a id="schemaruleresponse"></a>
<a id="schema_RuleResponse"></a>
<a id="tocSruleresponse"></a>
<a id="tocsruleresponse"></a>

```json
{
  "created": "2023-09-20T12:13:07.272753Z",
  "modified": "2023-09-20T12:13:07.272753Z",
  "id": 10,
  "name": "new rule",
  "variableName": "newRule",
  "description": "basic desecription",
  "status": "active",
  "condition": {
    "groupingType": "always",
    "customLogic": null,
    "scriptId": null,
    "conditions": []
  },
  "actions": [],
  "lastModifiedBy": "scheck@sm1.logik.dev"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|name|string|false|none|none|
|variableName|string|false|none|none|
|description|string|false|none|none|
|status|string|false|none|none|
|condition|object|false|none|none|
|» groupingType|string|false|none|none|
|» customLogic|string|false|none|none|
|» scriptId|string|false|none|none|
|» conditions|[any]|false|none|none|
|actions|[any]|false|none|none|
|lastModifiedBy|string|false|none|none|

<h2 id="tocS_RelatedFieldsResponse">RelatedFieldsResponse</h2>
<!-- backwards compatibility -->
<a id="schemarelatedfieldsresponse"></a>
<a id="schema_RelatedFieldsResponse"></a>
<a id="tocSrelatedfieldsresponse"></a>
<a id="tocsrelatedfieldsresponse"></a>

```json
{
  "content": [
    {
      "id": 2,
      "name": "Product Id (System)",
      "variableName": "sys.productId",
      "description": "System Field for the Id of the Configured Product",
      "type": "Text",
      "modified": "2000-01-01T00:00:00Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 4,
      "name": "Product Price (System)",
      "variableName": "sys.productPrice",
      "description": "System Field for the Base Price of the Configured Product",
      "type": "Number",
      "modified": "2000-01-01T00:00:00Z",
      "category": "SYSTEM",
      "lastModifiedBy": null
    },
    {
      "id": 56,
      "name": "uniqueId",
      "variableName": "psmPP.uniqueId",
      "description": null,
      "type": "Text",
      "modified": "2023-07-21T17:55:30.202817Z",
      "category": "PICKER_SUBFIELD",
      "lastModifiedBy": null
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalPages": 1,
  "totalElements": 6,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 6,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|true|none|none|
|»» name|string|true|none|none|
|»» variableName|string|true|none|none|
|»» description|string|true|none|none|
|»» type|string|true|none|none|
|»» modified|string|true|none|none|
|»» category|string|true|none|none|
|»» lastModifiedBy|string|true|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_RelatedBlueprintsResponse">RelatedBlueprintsResponse</h2>
<!-- backwards compatibility -->
<a id="schemarelatedblueprintsresponse"></a>
<a id="schema_RelatedBlueprintsResponse"></a>
<a id="tocSrelatedblueprintsresponse"></a>
<a id="tocsrelatedblueprintsresponse"></a>

```json
{
  "content": [
    {
      "id": 1,
      "name": "psmTester",
      "variableName": "psmTester",
      "description": "",
      "modified": "2023-09-08T20:54:24.225681Z",
      "lastModifiedBy": "scheck@sm1.logik.dev"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalPages": 1,
  "totalElements": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": false
  },
  "numberOfElements": 1,
  "first": true,
  "empty": false
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» content|[object]|false|none|none|
|»» id|number|false|none|none|
|»» name|string|false|none|none|
|»» variableName|string|false|none|none|
|»» description|string|false|none|none|
|»» modified|string|false|none|none|
|»» lastModifiedBy|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PagedResponse](#schemapagedresponse)|false|none|none|

<h2 id="tocS_MetadataPatch">MetadataPatch</h2>
<!-- backwards compatibility -->
<a id="schemametadatapatch"></a>
<a id="schema_MetadataPatch"></a>
<a id="tocSmetadatapatch"></a>
<a id="tocsmetadatapatch"></a>

```json
{
  "deleted": [
    "string"
  ],
  "added": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|deleted|[string]|false|none|none|
|added|[[Column](#schemacolumn)]|false|none|none|

<h2 id="tocS_Column">Column</h2>
<!-- backwards compatibility -->
<a id="schemacolumn"></a>
<a id="schema_Column"></a>
<a id="tocScolumn"></a>
<a id="tocscolumn"></a>

```json
{
  "name": "string",
  "type": "text",
  "description": "string",
  "orderNumber": 0
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ColumnMetadata](#schemacolumnmetadata)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» orderNumber|integer|false|none|none|

<h2 id="tocS_ColumnPatch">ColumnPatch</h2>
<!-- backwards compatibility -->
<a id="schemacolumnpatch"></a>
<a id="schema_ColumnPatch"></a>
<a id="tocScolumnpatch"></a>
<a id="tocscolumnpatch"></a>

```json
{
  "rows": [
    {
      "ID": 0,
      "additionalProperties": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rows|[[ColumnWithId](#schemacolumnwithid)]|true|none|none|

<h2 id="tocS_ColumnWithId">ColumnWithId</h2>
<!-- backwards compatibility -->
<a id="schemacolumnwithid"></a>
<a id="schema_ColumnWithId"></a>
<a id="tocScolumnwithid"></a>
<a id="tocscolumnwithid"></a>

```json
{
  "ID": 0,
  "additionalProperties": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ID|number|false|none|none|
|additionalProperties|string|false|none|none|

<h2 id="tocS_ColumnResponse">ColumnResponse</h2>
<!-- backwards compatibility -->
<a id="schemacolumnresponse"></a>
<a id="schema_ColumnResponse"></a>
<a id="tocScolumnresponse"></a>
<a id="tocscolumnresponse"></a>

```json
{
  "DATE_MODIFIED": "string",
  "DATE_CREATED": "string",
  "ID": 0,
  "additionalProperties": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» DATE_MODIFIED|string|false|none|none|
|» DATE_CREATED|string|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ColumnWithId](#schemacolumnwithid)|false|none|none|

<h2 id="tocS_Pageable">Pageable</h2>
<!-- backwards compatibility -->
<a id="schemapageable"></a>
<a id="schema_Pageable"></a>
<a id="tocSpageable"></a>
<a id="tocspageable"></a>

```json
{
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": true
  },
  "offset": 0,
  "pageNumber": 0,
  "pageSize": 0,
  "paged": true,
  "unpaged": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sort|object|false|none|none|
|» empty|boolean|false|none|none|
|» unsorted|boolean|false|none|none|
|» sorted|boolean|false|none|none|
|offset|number|false|none|none|
|pageNumber|number|false|none|none|
|pageSize|number|false|none|none|
|paged|boolean|false|none|none|
|unpaged|boolean|false|none|none|

<h2 id="tocS_TableResponse">TableResponse</h2>
<!-- backwards compatibility -->
<a id="schematableresponse"></a>
<a id="schema_TableResponse"></a>
<a id="tocStableresponse"></a>
<a id="tocstableresponse"></a>

```json
{
  "content": [
    {
      "DATE_MODIFIED": "string",
      "DATE_CREATED": "string",
      "ID": 0,
      "additionalProperties": "string"
    }
  ],
  "pageable": {
    "sort": {
      "empty": true,
      "unsorted": true,
      "sorted": true
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
  "sort": {
    "empty": true,
    "unsorted": true,
    "sorted": true
  },
  "first": true,
  "numberOfElements": 0,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|[[ColumnResponse](#schemacolumnresponse)]|false|none|none|
|pageable|[Pageable](#schemapageable)|false|none|none|
|totalPages|number|false|none|none|
|totalElements|number|false|none|none|
|last|boolean|false|none|none|
|size|number|false|none|none|
|number|number|false|none|none|
|sort|object|false|none|none|
|» empty|boolean|false|none|none|
|» unsorted|boolean|false|none|none|
|» sorted|boolean|false|none|none|
|first|boolean|false|none|none|
|numberOfElements|number|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_JobResponse">JobResponse</h2>
<!-- backwards compatibility -->
<a id="schemajobresponse"></a>
<a id="schema_JobResponse"></a>
<a id="tocSjobresponse"></a>
<a id="tocsjobresponse"></a>

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|started|string(date-time)|false|none|none|
|jobType|string|false|none|none|
|status|string|false|none|none|
|finished|string(date-time)¦null|false|none|none|

<h2 id="tocS_ImportTableResponse">ImportTableResponse</h2>
<!-- backwards compatibility -->
<a id="schemaimporttableresponse"></a>
<a id="schema_ImportTableResponse"></a>
<a id="tocSimporttableresponse"></a>
<a id="tocsimporttableresponse"></a>

```json
{
  "id": "6,",
  "started": "2023-05-31T02:51:16.550561712Z",
  "finished": null,
  "jobType": "TABLE_EXPORT",
  "status": "STARTED"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[JobResponse](#schemajobresponse)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ImportTableResult](#schemaimporttableresult)|false|none|none|

<h2 id="tocS_ImportTableResult">ImportTableResult</h2>
<!-- backwards compatibility -->
<a id="schemaimporttableresult"></a>
<a id="schema_ImportTableResult"></a>
<a id="tocSimporttableresult"></a>
<a id="tocsimporttableresult"></a>

```json
{
  "totalRecords": 0,
  "totalInserts": 0,
  "totalUpdates": 0,
  "tableName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalRecords|integer|false|none|none|
|totalInserts|integer|false|none|none|
|totalUpdates|integer|false|none|none|
|tableName|string|false|none|none|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "errorCode": "string",
  "errorMessage": "string",
  "timestamp": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|string|false|none|none|
|errorMessage|string|false|none|none|
|timestamp|string(date-time)|false|none|none|

<h2 id="tocS_ManagedTableCreateResponse">ManagedTableCreateResponse</h2>
<!-- backwards compatibility -->
<a id="schemamanagedtablecreateresponse"></a>
<a id="schema_ManagedTableCreateResponse"></a>
<a id="tocSmanagedtablecreateresponse"></a>
<a id="tocsmanagedtablecreateresponse"></a>

```json
{
  "dateCreated": "string",
  "dateModified": "string",
  "lastModifiedBy": "string",
  "name": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string",
      "orderNumber": 0
    }
  ],
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dateCreated|string|false|none|none|
|dateModified|string|false|none|none|
|lastModifiedBy|string|false|none|none|
|name|string|false|none|none|
|columns|[[Column](#schemacolumn)]|false|none|none|
|description|string|false|none|none|

<h2 id="tocS_ManagedTableCreatePayload">ManagedTableCreatePayload</h2>
<!-- backwards compatibility -->
<a id="schemamanagedtablecreatepayload"></a>
<a id="schema_ManagedTableCreatePayload"></a>
<a id="tocSmanagedtablecreatepayload"></a>
<a id="tocsmanagedtablecreatepayload"></a>

```json
{
  "name": "string",
  "description": "string",
  "columns": [
    {
      "name": "string",
      "type": "text",
      "description": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|string|true|none|none|
|columns|[[ColumnMetadata](#schemacolumnmetadata)]|true|none|none|

<h2 id="tocS_ColumnMetadata">ColumnMetadata</h2>
<!-- backwards compatibility -->
<a id="schemacolumnmetadata"></a>
<a id="schema_ColumnMetadata"></a>
<a id="tocScolumnmetadata"></a>
<a id="tocscolumnmetadata"></a>

```json
{
  "name": "string",
  "type": "text",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|type|string|true|none|none|
|description|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|text|
|type|number|

<h2 id="tocS_ManagedTableResponse">ManagedTableResponse</h2>
<!-- backwards compatibility -->
<a id="schemamanagedtableresponse"></a>
<a id="schema_ManagedTableResponse"></a>
<a id="tocSmanagedtableresponse"></a>
<a id="tocsmanagedtableresponse"></a>

```json
{
  "content": [
    {
      "dateCreated": "2023-05-30T21:19:32.650Z",
      "dateModified": "2023-05-30T21:19:55.210Z",
      "lastModifiedBy": "NO_USER_ID",
      "name": "packersTable",
      "columns": [
        {
          "name": "a",
          "type": "text",
          "description": "",
          "orderNumber": 1
        },
        {
          "name": "b",
          "type": "text",
          "description": "",
          "orderNumber": 2
        }
      ],
      "description": ""
    },
    {
      "dateCreated": "2023-05-31T02:34:32.749Z",
      "dateModified": "2023-05-31T02:34:32.749Z",
      "lastModifiedBy": "NO_USER_ID",
      "name": "shapes",
      "columns": [
        {
          "name": "sides",
          "type": "number",
          "description": "",
          "orderNumber": 1
        },
        {
          "name": "shape",
          "type": "text",
          "description": "",
          "orderNumber": 2
        }
      ],
      "description": ""
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "unsorted": false,
      "sorted": true
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 100,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "totalElements": 2,
  "last": true,
  "size": 100,
  "number": 0,
  "sort": {
    "empty": false,
    "unsorted": false,
    "sorted": true
  },
  "first": true,
  "numberOfElements": 2,
  "empty": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|[[ManagedTableCreateResponse](#schemamanagedtablecreateresponse)]|false|none|none|
|pageable|[Pageable](#schemapageable)|false|none|none|
|totalPages|number|false|none|none|
|totalElements|number|false|none|none|
|last|boolean|false|none|none|
|size|number|false|none|none|
|number|number|false|none|none|
|sort|object|false|none|none|
|» empty|boolean|false|none|none|
|» unsorted|boolean|false|none|none|
|» sorted|boolean|false|none|none|
|first|boolean|false|none|none|
|numberOfElements|number|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_MatrixLoaderUpload">MatrixLoaderUpload</h2>
<!-- backwards compatibility -->
<a id="schemamatrixloaderupload"></a>
<a id="schema_MatrixLoaderUpload"></a>
<a id="tocSmatrixloaderupload"></a>
<a id="tocsmatrixloaderupload"></a>

```json
{
  "jobType": "GENERIC_IMPORT",
  "file": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jobType|string|true|none|none|
|file|string(binary)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|jobType|GENERIC_IMPORT|
|jobType|RULE_IMPORT|
|jobType|FIELD_IMPORT|
|jobType|FIELD_OPTION_IMPORT|
|jobType|SETS|
|jobType|PRODUCT_PICKERS|
|jobType|BLUEPRINT_IMPORT|

<h2 id="tocS_MatrixLoaderGenericUploadResponse">MatrixLoaderGenericUploadResponse</h2>
<!-- backwards compatibility -->
<a id="schemamatrixloadergenericuploadresponse"></a>
<a id="schema_MatrixLoaderGenericUploadResponse"></a>
<a id="tocSmatrixloadergenericuploadresponse"></a>
<a id="tocsmatrixloadergenericuploadresponse"></a>

```json
{
  "created": "2023-09-19T16:40:26.550044863Z",
  "modified": "2023-09-19T16:40:26.550044863Z",
  "id": 99,
  "jobType": "GENERIC_IMPORT",
  "status": "STARTED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|string|false|none|none|
|modified|string|false|none|none|
|id|number|false|none|none|
|jobType|string|false|none|none|
|status|string|false|none|none|

<h2 id="tocS_ManagedTableDataUpload">ManagedTableDataUpload</h2>
<!-- backwards compatibility -->
<a id="schemamanagedtabledataupload"></a>
<a id="schema_ManagedTableDataUpload"></a>
<a id="tocSmanagedtabledataupload"></a>
<a id="tocsmanagedtabledataupload"></a>

```json
{
  "jobType": "MANAGED_TABLES_IMPORT_UPSERT",
  "file": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jobType|string|true|none|none|
|file|string(binary)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|jobType|MANAGED_TABLES_IMPORT_UPSERT|

<h2 id="tocS_AdminJobResponse">AdminJobResponse</h2>
<!-- backwards compatibility -->
<a id="schemaadminjobresponse"></a>
<a id="schema_AdminJobResponse"></a>
<a id="tocSadminjobresponse"></a>
<a id="tocsadminjobresponse"></a>

```json
{
  "id": 99,
  "started": "2023-09-19T16:40:26.554240Z",
  "finished": "2023-09-19T16:40:26.563650Z",
  "jobType": "GENERIC_IMPORT",
  "status": "COMPLETED",
  "result": {
    "success": true,
    "counts": {
      "success": 0,
      "error": 0,
      "warning": 0,
      "total": 0
    },
    "messages": []
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|started|string|false|none|none|
|finished|string|false|none|none|
|jobType|string|false|none|none|
|status|string|false|none|none|
|result|object|false|none|none|
|» success|boolean|false|none|none|
|» counts|object|false|none|none|
|»» success|integer|false|none|none|
|»» error|integer|false|none|none|
|»» warning|integer|false|none|none|
|»» total|integer|false|none|none|
|» messages|[any]|false|none|none|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "errorMessage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorMessage|string|false|none|none|

<h2 id="tocS_FieldPayload">FieldPayload</h2>
<!-- backwards compatibility -->
<a id="schemafieldpayload"></a>
<a id="schema_FieldPayload"></a>
<a id="tocSfieldpayload"></a>
<a id="tocsfieldpayload"></a>

```json
{
  "variableName": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|variableName|string|false|none|none|
|value|string|false|none|none|

<h2 id="tocS_UpdateConfig">UpdateConfig</h2>
<!-- backwards compatibility -->
<a id="schemaupdateconfig"></a>
<a id="schema_UpdateConfig"></a>
<a id="tocSupdateconfig"></a>
<a id="tocsupdateconfig"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fields|[[FieldPayload](#schemafieldpayload)]|false|none|none|

<h2 id="tocS_InitConfig">InitConfig</h2>
<!-- backwards compatibility -->
<a id="schemainitconfig"></a>
<a id="schema_InitConfig"></a>
<a id="tocSinitconfig"></a>
<a id="tocsinitconfig"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionContext|object|false|none|none|
|» stateful|boolean|false|none|none|
|partnerData|object|false|none|none|
|» product|object|true|none|none|
|»» configuredProductId|string|false|none|Product id of the Product linked to Logik Blueprint|
|»» configurationAttributes|object|false|none|none|
|»»» LGK__ConfigurationId__c|string|false|none|Configuration Id which was generated for saved configuration|
|quote|object|false|none|none|
|» SBQQ__PricebookId__c|string|false|none|none|
|fields|[[FieldPayload](#schemafieldpayload)]|false|none|none|

<h2 id="tocS_BOMResponse">BOMResponse</h2>
<!-- backwards compatibility -->
<a id="schemabomresponse"></a>
<a id="schema_BOMResponse"></a>
<a id="tocSbomresponse"></a>
<a id="tocsbomresponse"></a>

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
      "extPrice": 0
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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[[Product](#schemaproduct)]|false|none|none|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» offset|integer|false|none|none|
|» pageNumber|integer|false|none|none|
|» pageSize|integer|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|integer|false|none|none|
|totalElements|integer|false|none|none|
|last|boolean|false|none|none|
|size|integer|false|none|none|
|number|integer|false|none|none|
|numberOfElements|integer|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_Product">Product</h2>
<!-- backwards compatibility -->
<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|selectionType|string|false|none|none|
|quantity|integer|false|none|none|
|bomType|string|false|none|none|
|level|integer|false|none|none|
|parentProduct|integer|false|none|none|
|notes|string|false|none|none|
|uniqueIdentifier|integer|false|none|none|
|description|string|false|none|none|
|externalId|string|false|none|none|
|name|string|false|none|none|
|price|number|false|none|none|
|extPrice|number|false|none|none|

<h2 id="tocS_Field">Field</h2>
<!-- backwards compatibility -->
<a id="schemafield"></a>
<a id="schema_Field"></a>
<a id="tocSfield"></a>
<a id="tocsfield"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string|false|none|none|
|dataType|string|false|none|none|
|visibilityState|string|false|none|none|
|editable|string|false|none|none|
|variableName|string|false|none|none|
|optionSet|object|false|none|none|
|» options|[object]|true|none|none|
|»» label|string|true|none|none|
|»» state|string|true|none|none|
|»» value|string|true|none|none|
|»» imageUrl|string|false|none|none|
|»» orderNumber|integer|true|none|none|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "message": "string",
  "type": "string",
  "error": true,
  "field": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|
|type|string|true|none|none|
|error|boolean|true|none|none|
|field|string|true|none|none|

<h2 id="tocS_ConfigResponse">ConfigResponse</h2>
<!-- backwards compatibility -->
<a id="schemaconfigresponse"></a>
<a id="schema_ConfigResponse"></a>
<a id="tocSconfigresponse"></a>
<a id="tocsconfigresponse"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fields|[[Field](#schemafield)]|false|none|none|
|uuid|string|false|none|none|
|revision|integer|false|none|none|
|valid|boolean|false|none|none|
|messages|[[Message](#schemamessage)]|false|none|none|
|productChange|boolean|false|none|none|
|products|[[Product](#schemaproduct)]|false|none|none|
|layouts|[object]|false|none|none|
|» url|string|true|none|none|
|relatedChanges|[[relatedChangesValue](#schemarelatedchangesvalue)]|false|none|none|

<h2 id="tocS_relatedChangesValue">relatedChangesValue</h2>
<!-- backwards compatibility -->
<a id="schemarelatedchangesvalue"></a>
<a id="schema_relatedChangesValue"></a>
<a id="tocSrelatedchangesvalue"></a>
<a id="tocsrelatedchangesvalue"></a>

```json
{
  "key": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|false|none|none|
|type|string|false|none|Value of SET|PRODUCT which will return KEY value as variable name of set or static value products|

<h2 id="tocS_SetsContent">SetsContent</h2>
<!-- backwards compatibility -->
<a id="schemasetscontent"></a>
<a id="schema_SetsContent"></a>
<a id="tocSsetscontent"></a>
<a id="tocssetscontent"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|index|integer|false|none|none|
|fields|[[Field](#schemafield)]|false|none|none|

<h2 id="tocS_SetsResponse">SetsResponse</h2>
<!-- backwards compatibility -->
<a id="schemasetsresponse"></a>
<a id="schema_SetsResponse"></a>
<a id="tocSsetsresponse"></a>
<a id="tocssetsresponse"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|[[SetsContent](#schemasetscontent)]|false|none|none|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» offset|integer|false|none|none|
|» pageNumber|integer|false|none|none|
|» pageSize|integer|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|integer|false|none|none|
|totalElements|integer|false|none|none|
|last|boolean|false|none|none|
|size|integer|false|none|none|
|number|integer|false|none|none|
|numberOfElements|integer|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_UpdateConfigV2">UpdateConfigV2</h2>
<!-- backwards compatibility -->
<a id="schemaupdateconfigv2"></a>
<a id="schema_UpdateConfigV2"></a>
<a id="tocSupdateconfigv2"></a>
<a id="tocsupdateconfigv2"></a>

```json
{
  "fields": [
    {
      "variableName": "cpuPicker.select",
      "uniqueName": "cpuPicker-1003-cpuPicker.select",
      "value": true,
      "set": "cpuPicker",
      "index": 3
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fields|[object]|false|none|none|
|» variableName|string|false|none|none|
|» value|boolean|false|none|none|
|» index|number|false|none|none|
|» set|string|false|none|none|
|» uniqueName|string|false|none|none|
|responseState|object|false|none|none|
|» setPagination|object|false|none|none|
|»» additionalProperties|object|false|none|none|
|»»» pageSize|number|true|none|none|
|»»» pageNumber|number|true|none|none|
|» defaultPagination|object|false|none|none|
|»» pageSize|number|true|none|none|
|»» pageNumber|number|true|none|none|

<h2 id="tocS_InitConfigV2">InitConfigV2</h2>
<!-- backwards compatibility -->
<a id="schemainitconfigv2"></a>
<a id="schema_InitConfigV2"></a>
<a id="tocSinitconfigv2"></a>
<a id="tocsinitconfigv2"></a>

```json
{
  "sessionContext": {
    "stateful": true
  },
  "productId": "01t6e000009bOeLAAU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionContext|object|false|none|none|
|» stateful|boolean|true|none|none|
|partnerData|object|false|none|none|
|» quote|object|false|none|none|
|»» SBQQ__PricebookId__c|string|false|none|none|
|»» LGK__QueriedEditAccess__c|string|false|none|none|
|» product|object|false|none|none|
|»» configuredProductId|string|false|none|none|
|»» configurationAttributes|object|false|none|none|
|»»» LGK__Logik_Id__c|string|false|none|none|
|configurableProduct|object|false|none|none|
|» responseState|object|false|none|none|
|»» defaultPagination|object|true|none|none|
|»»» pageSize|number|true|none|none|
|»»» pageNumber|number|true|none|none|
|productId|string|false|none|none|

<h2 id="tocS_BOMResponse">BOMResponse</h2>
<!-- backwards compatibility -->
<a id="schemabomresponse"></a>
<a id="schema_BOMResponse"></a>
<a id="tocSbomresponse"></a>
<a id="tocsbomresponse"></a>

```json
{
  "total": 350,
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 20,
    "paged": true,
    "unpaged": false
  },
  "totalPages": 1,
  "totalElements": 2,
  "last": true,
  "size": 20,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "numberOfElements": 2,
  "first": true,
  "empty": false,
  "products": [
    {
      "id": "SSM",
      "uom": "",
      "name": "Single Motherboard",
      "type": "accessory",
      "level": 0,
      "price": 125,
      "bomType": "Sales",
      "extPrice": 125,
      "quantity": 1,
      "partnerId": "01t6e000009gRTpAAM",
      "externalId": "",
      "description": "",
      "orderNumber": 10,
      "productCode": "SSM",
      "rollUpPrice": 350,
      "productFamily": "",
      "uniqueIdentifier": "motherboard"
    },
    {
      "id": "CPU7320GHZRYZ3",
      "uom": "",
      "name": "AMD Ryzen 3 7320U",
      "type": "accessory",
      "level": 1,
      "price": 225,
      "bomType": "SALES",
      "extPrice": 225,
      "extended": {
        "watts": "150"
      },
      "quantity": 1,
      "partnerId": "01t6e000009bOfYAAU",
      "externalId": "",
      "description": "",
      "productCode": "CPU7320GHZRYZ3",
      "rollUpPrice": 225,
      "parentProduct": "motherboard",
      "productFamily": "Hardware",
      "effectiveParent": "motherboard"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[[Product](#schemaproduct)]|false|none|none|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» offset|integer|false|none|none|
|» pageNumber|integer|false|none|none|
|» pageSize|integer|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|integer|false|none|none|
|totalElements|integer|false|none|none|
|last|boolean|false|none|none|
|size|integer|false|none|none|
|number|integer|false|none|none|
|numberOfElements|integer|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_Product">Product</h2>
<!-- backwards compatibility -->
<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|selectionType|string|false|none|none|
|quantity|integer|false|none|none|
|bomType|string|false|none|none|
|level|integer|false|none|none|
|parentProduct|integer|false|none|none|
|notes|string|false|none|none|
|uniqueIdentifier|integer|false|none|none|
|description|string|false|none|none|
|externalId|string|false|none|none|
|name|string|false|none|none|
|price|number|false|none|none|
|extPrice|number|false|none|none|

<h2 id="tocS_Field">Field</h2>
<!-- backwards compatibility -->
<a id="schemafield"></a>
<a id="schema_Field"></a>
<a id="tocSfield"></a>
<a id="tocsfield"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string|false|none|none|
|dataType|string|false|none|none|
|visibilityState|string|false|none|none|
|editable|string|false|none|none|
|variableName|string|false|none|none|
|optionSet|object|false|none|none|
|» options|[object]|true|none|none|
|»» label|string|true|none|none|
|»» state|string|true|none|none|
|»» value|string|true|none|none|
|»» imageUrl|string|false|none|none|
|»» orderNumber|integer|true|none|none|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "message": "string",
  "type": "string",
  "error": true,
  "field": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|
|type|string|true|none|none|
|error|boolean|true|none|none|
|field|string|true|none|none|

<h2 id="tocS_relatedChangesValue">relatedChangesValue</h2>
<!-- backwards compatibility -->
<a id="schemarelatedchangesvalue"></a>
<a id="schema_relatedChangesValue"></a>
<a id="tocSrelatedchangesvalue"></a>
<a id="tocsrelatedchangesvalue"></a>

```json
{
  "key": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|false|none|none|
|type|string|false|none|Value of SET|PRODUCT which will return KEY value as variable name of set or static value products|

<h2 id="tocS_SetsContent">SetsContent</h2>
<!-- backwards compatibility -->
<a id="schemasetscontent"></a>
<a id="schema_SetsContent"></a>
<a id="tocSsetscontent"></a>
<a id="tocssetscontent"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|index|integer|false|none|none|
|fields|[[Field](#schemafield)]|false|none|none|

<h2 id="tocS_SetsResponse">SetsResponse</h2>
<!-- backwards compatibility -->
<a id="schemasetsresponse"></a>
<a id="schema_SetsResponse"></a>
<a id="tocSsetsresponse"></a>
<a id="tocssetsresponse"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|[[SetsContent](#schemasetscontent)]|false|none|none|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» offset|integer|false|none|none|
|» pageNumber|integer|false|none|none|
|» pageSize|integer|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|integer|false|none|none|
|totalElements|integer|false|none|none|
|last|boolean|false|none|none|
|size|integer|false|none|none|
|number|integer|false|none|none|
|numberOfElements|integer|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_ConfigResponseV2">ConfigResponseV2</h2>
<!-- backwards compatibility -->
<a id="schemaconfigresponsev2"></a>
<a id="schema_ConfigResponseV2"></a>
<a id="tocSconfigresponsev2"></a>
<a id="tocsconfigresponsev2"></a>

```json
{
  "fields": [
    {
      "userEdited": false,
      "dataType": "array",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "ramPicker",
      "uniqueName": "ramPicker",
      "value": [],
      "optionSet": {
        "options": [
          {
            "label": "8GB RAM Module",
            "state": "visible",
            "value": "RAM8GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 10
          },
          {
            "label": "16GB RAM Module",
            "state": "visible",
            "value": "RAM16GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 20
          },
          {
            "label": "32GB RAM Module",
            "state": "visible",
            "value": "RAM32GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 30
          }
        ]
      },
      "selectAll": "NONE",
      "rows": {
        "content": [
          {
            "index": 0,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.value",
                "uniqueName": "ramPicker-1000-ramPicker.value",
                "value": "RAM8GB",
                "set": "ramPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.interface",
                "uniqueName": "ramPicker-1000-ramPicker.interface",
                "value": "DDR4",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "DDR4",
                      "state": "visible",
                      "value": "DDR4",
                      "imageUrl": null,
                      "orderNumber": 10
                    }
                  ],
                  "options": [
                    {
                      "label": "DDR4",
                      "state": "visible",
                      "value": "DDR4",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "DDR5",
                      "state": "visible",
                      "value": "DDR5",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.select",
                "uniqueName": "ramPicker-1000-ramPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.quantity",
                "uniqueName": "ramPicker-1000-ramPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "ramPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.imageUrl",
                "uniqueName": "ramPicker-1000-ramPicker.imageUrl",
                "value": "",
                "set": "ramPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.storage",
                "uniqueName": "ramPicker-1000-ramPicker.storage",
                "value": 0,
                "set": "ramPicker",
                "index": 0
              }
            ],
            "label": "8GB RAM Module",
            "state": "visible",
            "value": "RAM8GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 10,
            "productDetails": {
              "price": 50,
              "name": "RAM 8GB"
            }
          },
          {
            "index": 1,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.value",
                "uniqueName": "ramPicker-1001-ramPicker.value",
                "value": "RAM16GB",
                "set": "ramPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.interface",
                "uniqueName": "ramPicker-1001-ramPicker.interface",
                "value": "DDR4",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "DDR4",
                      "state": "visible",
                      "value": "DDR4",
                      "imageUrl": null,
                      "orderNumber": 10
                    }
                  ],
                  "options": [
                    {
                      "label": "DDR4",
                      "state": "visible",
                      "value": "DDR4",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "DDR5",
                      "state": "visible",
                      "value": "DDR5",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.select",
                "uniqueName": "ramPicker-1001-ramPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.quantity",
                "uniqueName": "ramPicker-1001-ramPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "ramPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.imageUrl",
                "uniqueName": "ramPicker-1001-ramPicker.imageUrl",
                "value": "",
                "set": "ramPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.storage",
                "uniqueName": "ramPicker-1001-ramPicker.storage",
                "value": 0,
                "set": "ramPicker",
                "index": 1
              }
            ],
            "label": "16GB RAM Module",
            "state": "visible",
            "value": "RAM16GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 20,
            "productDetails": {
              "price": 125,
              "name": "RAM 16GB"
            }
          },
          {
            "index": 2,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.value",
                "uniqueName": "ramPicker-1002-ramPicker.value",
                "value": "RAM32GB",
                "set": "ramPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.interface",
                "uniqueName": "ramPicker-1002-ramPicker.interface",
                "value": "DDR5",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "DDR5",
                      "state": "visible",
                      "value": "DDR5",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ],
                  "options": [
                    {
                      "label": "DDR4",
                      "state": "visible",
                      "value": "DDR4",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "DDR5",
                      "state": "visible",
                      "value": "DDR5",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.select",
                "uniqueName": "ramPicker-1002-ramPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "ramPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.quantity",
                "uniqueName": "ramPicker-1002-ramPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "ramPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "ramPicker.imageUrl",
                "uniqueName": "ramPicker-1002-ramPicker.imageUrl",
                "value": "",
                "set": "ramPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "ramPicker.storage",
                "uniqueName": "ramPicker-1002-ramPicker.storage",
                "value": 0,
                "set": "ramPicker",
                "index": 2
              }
            ],
            "label": "32GB RAM Module",
            "state": "visible",
            "value": "RAM32GB",
            "imageUrl": "https://i.imgur.com/WkXo98I.png",
            "orderNumber": 30,
            "productDetails": {
              "price": 175,
              "name": "RAM 32GB"
            }
          }
        ],
        "pageable": "INSTANCE",
        "totalPages": 1,
        "totalElements": 3,
        "last": true,
        "size": 3,
        "number": 0,
        "sort": {
          "empty": true,
          "sorted": false,
          "unsorted": true
        },
        "numberOfElements": 3,
        "first": true,
        "empty": false
      }
    },
    {
      "userEdited": false,
      "dataType": "array",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "drivePicker",
      "uniqueName": "drivePicker",
      "value": [],
      "optionSet": {
        "options": [
          {
            "label": "SSD128",
            "state": "visible",
            "value": "SSD128",
            "imageUrl": null,
            "orderNumber": 10
          },
          {
            "label": "SSD256",
            "state": "visible",
            "value": "SSD256",
            "imageUrl": null,
            "orderNumber": 20
          },
          {
            "label": "SSD512",
            "state": "visible",
            "value": "SSD512",
            "imageUrl": null,
            "orderNumber": 30
          }
        ]
      },
      "selectAll": "NONE",
      "rows": {
        "content": [
          {
            "index": 0,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "drivePicker.value",
                "uniqueName": "drivePicker-1000-drivePicker.value",
                "value": "SSD128",
                "set": "drivePicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.select",
                "uniqueName": "drivePicker-1000-drivePicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.quantity",
                "uniqueName": "drivePicker-1000-drivePicker.quantity",
                "value": 0,
                "set": "drivePicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.interface",
                "uniqueName": "drivePicker-1000-drivePicker.interface",
                "value": "NVMe",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "NVMe",
                      "state": "visible",
                      "value": "NVMe",
                      "imageUrl": null,
                      "orderNumber": 10
                    }
                  ],
                  "options": [
                    {
                      "label": "NVMe",
                      "state": "visible",
                      "value": "NVMe",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "SSD",
                      "state": "visible",
                      "value": "SSD",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 0
              }
            ],
            "label": "SSD128",
            "state": "visible",
            "value": "SSD128",
            "imageUrl": null,
            "orderNumber": 10,
            "productDetails": {
              "price": 89,
              "name": "NVMe Drive 128GB",
              "description": "Lightning fast Storage for all your computing needs"
            }
          },
          {
            "index": 1,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "drivePicker.value",
                "uniqueName": "drivePicker-1001-drivePicker.value",
                "value": "SSD256",
                "set": "drivePicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.select",
                "uniqueName": "drivePicker-1001-drivePicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.quantity",
                "uniqueName": "drivePicker-1001-drivePicker.quantity",
                "value": 0,
                "set": "drivePicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.interface",
                "uniqueName": "drivePicker-1001-drivePicker.interface",
                "value": "SSD",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "SSD",
                      "state": "visible",
                      "value": "SSD",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ],
                  "options": [
                    {
                      "label": "NVMe",
                      "state": "visible",
                      "value": "NVMe",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "SSD",
                      "state": "visible",
                      "value": "SSD",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 1
              }
            ],
            "label": "SSD256",
            "state": "visible",
            "value": "SSD256",
            "imageUrl": null,
            "orderNumber": 20,
            "productDetails": {
              "price": 75,
              "name": "SSD 256GB",
              "description": "A balance of speed and capacity"
            }
          },
          {
            "index": 2,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "drivePicker.value",
                "uniqueName": "drivePicker-1002-drivePicker.value",
                "value": "SSD512",
                "set": "drivePicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.select",
                "uniqueName": "drivePicker-1002-drivePicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.quantity",
                "uniqueName": "drivePicker-1002-drivePicker.quantity",
                "value": 0,
                "set": "drivePicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "drivePicker.interface",
                "uniqueName": "drivePicker-1002-drivePicker.interface",
                "value": "SSD",
                "optionSet": {
                  "selectedOptions": [
                    {
                      "label": "SSD",
                      "state": "visible",
                      "value": "SSD",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ],
                  "options": [
                    {
                      "label": "NVMe",
                      "state": "visible",
                      "value": "NVMe",
                      "imageUrl": null,
                      "orderNumber": 10
                    },
                    {
                      "label": "SSD",
                      "state": "visible",
                      "value": "SSD",
                      "imageUrl": null,
                      "orderNumber": 20
                    }
                  ]
                },
                "set": "drivePicker",
                "index": 2
              }
            ],
            "label": "SSD512",
            "state": "visible",
            "value": "SSD512",
            "imageUrl": null,
            "orderNumber": 30,
            "productDetails": {
              "price": 150,
              "name": "SSD 512GB",
              "description": "Bulk SSD Storage for large files"
            }
          }
        ],
        "pageable": "INSTANCE",
        "totalPages": 1,
        "totalElements": 3,
        "last": true,
        "size": 3,
        "number": 0,
        "sort": {
          "empty": true,
          "sorted": false,
          "unsorted": true
        },
        "numberOfElements": 3,
        "first": true,
        "empty": false
      }
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "cpuPicker",
      "uniqueName": "cpuPicker",
      "value": "",
      "optionSet": {
        "options": [
          {
            "label": "Dual Core Processor",
            "state": "visible",
            "value": "CPU16GHZI5",
            "imageUrl": "https://i.imgur.com/ftft5Nx.png",
            "orderNumber": 10
          },
          {
            "label": "Quad Core Processor",
            "state": "visible",
            "value": "CPU22GHZI7",
            "imageUrl": "https://i.imgur.com/ftft5Nx.png",
            "orderNumber": 20
          },
          {
            "label": "6-Core Processor",
            "state": "visible",
            "value": "CPU28GHZI7",
            "imageUrl": "https://i.imgur.com/0xQH6mZ.png",
            "orderNumber": 30
          },
          {
            "label": "8-Core Processor",
            "state": "visible",
            "value": "CPU7320GHZRYZ3",
            "imageUrl": "https://i.imgur.com/0xQH6mZ.png",
            "orderNumber": 40
          },
          {
            "label": "12-Core Processor",
            "state": "visible",
            "value": "CPU7550GHZRYZ5",
            "imageUrl": "https://i.imgur.com/LaQVZma.png",
            "orderNumber": 50
          }
        ]
      },
      "rows": {
        "content": [
          {
            "index": 0,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "cpuPicker.value",
                "uniqueName": "cpuPicker-1000-cpuPicker.value",
                "value": "CPU16GHZI5",
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.select",
                "uniqueName": "cpuPicker-1000-cpuPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.quantity",
                "uniqueName": "cpuPicker-1000-cpuPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.imageUrl",
                "uniqueName": "cpuPicker-1000-cpuPicker.imageUrl",
                "value": "",
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.description",
                "uniqueName": "cpuPicker-1000-cpuPicker.description",
                "value": "Processor for light computing",
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.price",
                "uniqueName": "cpuPicker-1000-cpuPicker.price",
                "value": 100,
                "set": "cpuPicker",
                "index": 0
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.watts",
                "uniqueName": "cpuPicker-1000-cpuPicker.watts",
                "value": 75,
                "set": "cpuPicker",
                "index": 0
              }
            ],
            "label": "Dual Core Processor",
            "state": "visible",
            "value": "CPU16GHZI5",
            "imageUrl": "https://i.imgur.com/ftft5Nx.png",
            "orderNumber": 10,
            "productDetails": {
              "name": "CPU 1.6GHz i5"
            }
          },
          {
            "index": 1,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "cpuPicker.value",
                "uniqueName": "cpuPicker-1001-cpuPicker.value",
                "value": "CPU22GHZI7",
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.select",
                "uniqueName": "cpuPicker-1001-cpuPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.quantity",
                "uniqueName": "cpuPicker-1001-cpuPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.imageUrl",
                "uniqueName": "cpuPicker-1001-cpuPicker.imageUrl",
                "value": "",
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.description",
                "uniqueName": "cpuPicker-1001-cpuPicker.description",
                "value": "Processor for light computing and office work",
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.price",
                "uniqueName": "cpuPicker-1001-cpuPicker.price",
                "value": 125,
                "set": "cpuPicker",
                "index": 1
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.watts",
                "uniqueName": "cpuPicker-1001-cpuPicker.watts",
                "value": 100,
                "set": "cpuPicker",
                "index": 1
              }
            ],
            "label": "Quad Core Processor",
            "state": "visible",
            "value": "CPU22GHZI7",
            "imageUrl": "https://i.imgur.com/ftft5Nx.png",
            "orderNumber": 20,
            "productDetails": {
              "name": "CPU 2.2GHz i7"
            }
          },
          {
            "index": 2,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "cpuPicker.value",
                "uniqueName": "cpuPicker-1002-cpuPicker.value",
                "value": "CPU28GHZI7",
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.select",
                "uniqueName": "cpuPicker-1002-cpuPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.quantity",
                "uniqueName": "cpuPicker-1002-cpuPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.imageUrl",
                "uniqueName": "cpuPicker-1002-cpuPicker.imageUrl",
                "value": "",
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.description",
                "uniqueName": "cpuPicker-1002-cpuPicker.description",
                "value": "Perfect for moderate computing tasks",
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.price",
                "uniqueName": "cpuPicker-1002-cpuPicker.price",
                "value": 175,
                "set": "cpuPicker",
                "index": 2
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.watts",
                "uniqueName": "cpuPicker-1002-cpuPicker.watts",
                "value": 125,
                "set": "cpuPicker",
                "index": 2
              }
            ],
            "label": "6-Core Processor",
            "state": "visible",
            "value": "CPU28GHZI7",
            "imageUrl": "https://i.imgur.com/0xQH6mZ.png",
            "orderNumber": 30,
            "productDetails": {
              "name": "CPU 2.8GHz i7"
            }
          },
          {
            "index": 3,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "cpuPicker.value",
                "uniqueName": "cpuPicker-1003-cpuPicker.value",
                "value": "CPU7320GHZRYZ3",
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.select",
                "uniqueName": "cpuPicker-1003-cpuPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.quantity",
                "uniqueName": "cpuPicker-1003-cpuPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.imageUrl",
                "uniqueName": "cpuPicker-1003-cpuPicker.imageUrl",
                "value": "",
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.description",
                "uniqueName": "cpuPicker-1003-cpuPicker.description",
                "value": "Great 3D and Video editing capabilities",
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.price",
                "uniqueName": "cpuPicker-1003-cpuPicker.price",
                "value": 225,
                "set": "cpuPicker",
                "index": 3
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.watts",
                "uniqueName": "cpuPicker-1003-cpuPicker.watts",
                "value": 150,
                "set": "cpuPicker",
                "index": 3
              }
            ],
            "label": "8-Core Processor",
            "state": "visible",
            "value": "CPU7320GHZRYZ3",
            "imageUrl": "https://i.imgur.com/0xQH6mZ.png",
            "orderNumber": 40,
            "productDetails": {
              "name": "AMD Ryzen 3 7320U"
            }
          },
          {
            "index": 4,
            "fields": [
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "false",
                "variableName": "cpuPicker.value",
                "uniqueName": "cpuPicker-1004-cpuPicker.value",
                "value": "CPU7550GHZRYZ5",
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "boolean",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.select",
                "uniqueName": "cpuPicker-1004-cpuPicker.select",
                "value": false,
                "optionSet": {
                  "options": [
                    {
                      "label": "true",
                      "state": "visible",
                      "value": "true",
                      "imageUrl": null,
                      "orderNumber": null
                    },
                    {
                      "label": "false",
                      "state": "visible",
                      "value": "false",
                      "imageUrl": null,
                      "orderNumber": null
                    }
                  ]
                },
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.quantity",
                "uniqueName": "cpuPicker-1004-cpuPicker.quantity",
                "value": 0,
                "step": 1,
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.imageUrl",
                "uniqueName": "cpuPicker-1004-cpuPicker.imageUrl",
                "value": "",
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "text",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.description",
                "uniqueName": "cpuPicker-1004-cpuPicker.description",
                "value": "Top of the line processor for AI, number crunching and cryptography",
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.price",
                "uniqueName": "cpuPicker-1004-cpuPicker.price",
                "value": 325,
                "set": "cpuPicker",
                "index": 4
              },
              {
                "userEdited": false,
                "dataType": "number",
                "visibilityState": "visible",
                "editable": "true",
                "variableName": "cpuPicker.watts",
                "uniqueName": "cpuPicker-1004-cpuPicker.watts",
                "value": 225,
                "set": "cpuPicker",
                "index": 4
              }
            ],
            "label": "12-Core Processor",
            "state": "visible",
            "value": "CPU7550GHZRYZ5",
            "imageUrl": "https://i.imgur.com/LaQVZma.png",
            "orderNumber": 50,
            "productDetails": {
              "name": "AMD Ryzen 5 7550U"
            }
          }
        ],
        "pageable": "INSTANCE",
        "totalPages": 1,
        "totalElements": 5,
        "last": true,
        "size": 5,
        "number": 0,
        "sort": {
          "empty": true,
          "sorted": false,
          "unsorted": true
        },
        "numberOfElements": 5,
        "first": true,
        "empty": false
      }
    },
    {
      "userEdited": false,
      "dataType": "set",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "delta",
      "uniqueName": "delta",
      "rows": {
        "content": [],
        "pageable": "INSTANCE",
        "totalPages": 1,
        "totalElements": 0,
        "last": true,
        "size": 0,
        "number": 0,
        "sort": {
          "empty": true,
          "sorted": false,
          "unsorted": true
        },
        "numberOfElements": 0,
        "first": true,
        "empty": true
      }
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "false",
      "variableName": "ramPicker.aggregates.storage_sum",
      "uniqueName": "ramPicker.aggregates.storage_sum",
      "value": 0
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productDescription",
      "uniqueName": "sys.productDescription",
      "value": ""
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productUOM",
      "uniqueName": "sys.productUOM",
      "value": ""
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productPrice",
      "uniqueName": "sys.productPrice",
      "value": 0
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productId",
      "uniqueName": "sys.productId",
      "value": "SWC"
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.actionContext",
      "uniqueName": "sys.actionContext",
      "value": ""
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "set.delta.size",
      "uniqueName": "set.delta.size",
      "value": []
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "false",
      "variableName": "set.delta.priceSum",
      "uniqueName": "set.delta.priceSum",
      "value": 0
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productName",
      "uniqueName": "sys.productName",
      "value": "Laptop Configurator"
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "false",
      "variableName": "cpuPicker.aggregates.watts_sum",
      "uniqueName": "cpuPicker.aggregates.watts_sum",
      "value": 0
    },
    {
      "userEdited": false,
      "dataType": "number",
      "visibilityState": "visible",
      "editable": "false",
      "variableName": "ramPicker.aggregates.value_count",
      "uniqueName": "ramPicker.aggregates.value_count",
      "value": 0
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "pleExtension",
      "uniqueName": "pleExtension",
      "value": "SSM",
      "optionSet": {
        "selectedOptions": [
          {
            "label": "Single",
            "state": "visible",
            "value": "SSM",
            "imageUrl": null,
            "orderNumber": 10
          }
        ],
        "options": [
          {
            "label": "Single",
            "state": "visible",
            "value": "SSM",
            "imageUrl": null,
            "orderNumber": 10
          },
          {
            "label": "Dual",
            "state": "visible",
            "value": "DSM",
            "imageUrl": null,
            "orderNumber": 20
          }
        ]
      }
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "partner.quote.currencyIsoCode",
      "uniqueName": "partner.quote.currencyIsoCode",
      "value": "USD"
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productFamily",
      "uniqueName": "sys.productFamily",
      "value": "Software"
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "partner.quote.lineId",
      "uniqueName": "partner.quote.lineId",
      "value": ""
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.currentDate",
      "uniqueName": "sys.currentDate",
      "value": "2023-09-29"
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "cPUType",
      "uniqueName": "cPUType",
      "value": "All",
      "optionSet": {
        "selectedOptions": [
          {
            "label": "All",
            "state": "visible",
            "value": "All",
            "imageUrl": null,
            "orderNumber": 5
          }
        ],
        "options": [
          {
            "label": "All",
            "state": "visible",
            "value": "All",
            "imageUrl": null,
            "orderNumber": 5
          },
          {
            "label": "Low",
            "state": "visible",
            "value": "Low",
            "imageUrl": null,
            "orderNumber": 7
          },
          {
            "label": "Mid",
            "state": "visible",
            "value": "Mid",
            "imageUrl": null,
            "orderNumber": 8
          },
          {
            "label": "High",
            "state": "visible",
            "value": "High",
            "imageUrl": null,
            "orderNumber": 9
          }
        ]
      }
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "preconfigured",
      "uniqueName": "preconfigured",
      "value": "",
      "optionSet": {
        "options": [
          {
            "label": "Basic Office",
            "state": "visible",
            "value": "Basic",
            "imageUrl": null,
            "orderNumber": 10
          },
          {
            "label": "Video and 3D",
            "state": "visible",
            "value": "3D",
            "imageUrl": null,
            "orderNumber": 20
          },
          {
            "label": "Enthusiast",
            "state": "visible",
            "value": "Max",
            "imageUrl": null,
            "orderNumber": 30
          }
        ]
      }
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "sys.productCode",
      "uniqueName": "sys.productCode",
      "value": "SWC"
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "partner.quote.pricebookId",
      "uniqueName": "partner.quote.pricebookId",
      "value": ""
    },
    {
      "userEdited": false,
      "dataType": "text",
      "visibilityState": "visible",
      "editable": "true",
      "variableName": "partner.quote.id",
      "uniqueName": "partner.quote.id",
      "value": ""
    }
  ],
  "uuid": "ad947503-5246-461f-8603-f0124593ae1c",
  "revision": 0,
  "relatedChanges": [
    {
      "key": "drivePicker",
      "type": "PRODUCT_PICKER"
    },
    {
      "key": "ramPicker",
      "type": "PRODUCT_PICKER"
    },
    {
      "key": "cpuPicker",
      "type": "PRODUCT_PICKER"
    },
    {
      "key": "delta",
      "type": "SET"
    },
    {
      "key": "products",
      "type": "PRODUCT"
    }
  ],
  "valid": true,
  "messages": [],
  "productChange": true,
  "products": [
    {
      "id": "SSM",
      "quantity": 1,
      "bomType": "Sales",
      "price": 125,
      "uniqueIdentifier": "motherboard",
      "orderNumber": 10,
      "type": "accessory",
      "name": "Single Motherboard",
      "partnerId": "01t6e000009gRTpAAM",
      "productCode": "SSM",
      "externalId": "",
      "productFamily": "",
      "description": "",
      "uom": "",
      "extPrice": 125,
      "level": 0,
      "rollUpPrice": 125
    }
  ],
  "showValidationButton": false,
  "total": 125,
  "layouts": [
    {
      "url": "/blueprints/8/revisions/LATEST/layouts/1",
      "label": "basic",
      "variableName": "pickerGeneral_basic"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fields|[object]|false|none|none|
|» userEdited|boolean|false|none|none|
|» dataType|string|false|none|none|
|» visibilityState|string|false|none|none|
|» editable|string|false|none|none|
|» variableName|string|false|none|none|
|» uniqueName|string|false|none|none|
|» value|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[string]|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» optionSet|object|false|none|none|
|»» options|[object]|true|none|none|
|»»» label|string|false|none|none|
|»»» state|string|false|none|none|
|»»» value|string|false|none|none|
|»»» imageUrl|string|false|none|none|
|»»» orderNumber|number|false|none|none|
|» selectAll|string|false|none|none|
|» rows|object|false|none|none|
|»» content|[object]|true|none|none|
|»»» index|number|false|none|none|
|»»» fields|[object]|false|none|none|
|»»»» userEdited|boolean|false|none|none|
|»»»» dataType|string|false|none|none|
|»»»» visibilityState|string|false|none|none|
|»»»» editable|string|false|none|none|
|»»»» variableName|string|false|none|none|
|»»»» uniqueName|string|false|none|none|
|»»»» value|string|false|none|none|
|»»»» set|string|false|none|none|
|»»»» index|number|false|none|none|
|»»» label|string|false|none|none|
|»»» state|string|false|none|none|
|»»» value|string|false|none|none|
|»»» imageUrl|string|false|none|none|
|»»» orderNumber|number|false|none|none|
|»»» productDetails|object|false|none|none|
|»»»» price|number|true|none|none|
|»»»» name|string|true|none|none|
|»» pageable|string|true|none|none|
|»» last|boolean|true|none|none|
|»» totalPages|number|true|none|none|
|»» totalElements|number|true|none|none|
|»» size|number|true|none|none|
|»» number|number|true|none|none|
|»» sort|object|true|none|none|
|»»» empty|boolean|true|none|none|
|»»» sorted|boolean|true|none|none|
|»»» unsorted|boolean|true|none|none|
|»» numberOfElements|number|true|none|none|
|»» first|boolean|true|none|none|
|»» empty|boolean|true|none|none|
|uuid|string|false|none|none|
|revision|number|false|none|none|
|relatedChanges|[object]|false|none|none|
|» key|string|false|none|none|
|» type|string|false|none|none|
|valid|boolean|false|none|none|
|messages|[[Message](#schemamessage)]|false|none|none|
|productChange|boolean|false|none|none|
|products|[[Product](#schemaproduct)]|false|none|none|
|showValidationButton|boolean|false|none|none|
|layouts|[object]|false|none|none|
|» url|string|false|none|none|
|» label|string|false|none|none|
|» variableName|string|false|none|none|

<h2 id="tocS_BOMResponse">BOMResponse</h2>
<!-- backwards compatibility -->
<a id="schemabomresponse"></a>
<a id="schema_BOMResponse"></a>
<a id="tocSbomresponse"></a>
<a id="tocsbomresponse"></a>

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

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[[Product](#schemaproduct)]|false|none|none|
|pageable|object|false|none|none|
|» sort|object|false|none|none|
|»» empty|boolean|false|none|none|
|»» sorted|boolean|false|none|none|
|»» unsorted|boolean|false|none|none|
|» offset|integer|false|none|none|
|» pageNumber|integer|false|none|none|
|» pageSize|integer|false|none|none|
|» paged|boolean|false|none|none|
|» unpaged|boolean|false|none|none|
|totalPages|integer|false|none|none|
|totalElements|integer|false|none|none|
|last|boolean|false|none|none|
|size|integer|false|none|none|
|number|integer|false|none|none|
|numberOfElements|integer|false|none|none|
|first|boolean|false|none|none|
|empty|boolean|false|none|none|
|total|integer|false|none|none|

<h2 id="tocS_Product">Product</h2>
<!-- backwards compatibility -->
<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

```json
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

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|selectionType|string|false|none|none|
|quantity|integer|false|none|none|
|bomType|string|false|none|none|
|level|integer|false|none|none|
|parentProduct|integer|false|none|none|
|notes|string|false|none|none|
|uniqueIdentifier|integer|false|none|none|
|description|string|false|none|none|
|externalId|string|false|none|none|
|name|string|false|none|none|
|price|number|false|none|none|
|extPrice|number|false|none|none|
|extended|object|false|none|none|
|» additionalProperties|string|false|none|none|
