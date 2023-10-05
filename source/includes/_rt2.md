<h1 id="logik-configurator-runtime-apis-v2-configuration">Configuration (V2)</h1>

Creating new configurations, reconfiguring existing configurations, making updates to a configuration and saving changes. Can be used for headless or custom UI implementations.

## Important Versioning Information

Blueprints that use Product Picker Fields ***must*** use the `application/vnd.logik.cfg-v2+json` Content-Type when making requests.

 The Runtime APIs are versioned using different Content-Types. There are 2 Content-Type formats, `application/json` for v1 and `application/vnd.logik.cfg-v2+json` for v2.

- `application/json`: can be used with regular Logik field types (number, boolean, text and picklist) and sets.
- `application/vnd.logik.cfg-v2+json`: can be used with all regular field types as well as Product Picker Fields.
  
The Accept Header should match the Content-Type being used, either:

- `application/json`: for v1.
- `application/vnd.logik.cfg-v2+json, application/json`: for v2.

<aside class="info">
Blueprints that use Product Picker Fields <strong>must</strong> use the Configuration V2 APIs.
</aside>

## Start Configuration (V2)

<a id="opIdstartConfigV2"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/vnd.logik.cfg-v2+json',
  'Accept': 'application/vnd.logik.cfg-v2+json',
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
  "productId": "01t6e000009bOeLAAU"
}';
const headers = {
  'Content-Type':'application/vnd.logik.cfg-v2+json',
  'Accept':'application/vnd.logik.cfg-v2+json',
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
  "productId": "01t6e000009bOeLAAU"
};
const headers = {
  'Content-Type':'application/vnd.logik.cfg-v2+json',
  'Accept':'application/vnd.logik.cfg-v2+json',
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
  -H 'Content-Type: application/vnd.logik.cfg-v2+json' \
  -H 'Accept: application/vnd.logik.cfg-v2+json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://{tenant}.{sector}.logik.io/api HTTP/1.1

Content-Type: application/vnd.logik.cfg-v2+json
Accept: application/vnd.logik.cfg-v2+json
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
  'Content-Type' => 'application/vnd.logik.cfg-v2+json',
  'Accept' => 'application/vnd.logik.cfg-v2+json',
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
        "Content-Type": []string{"application/vnd.logik.cfg-v2+json"},
        "Accept": []string{"application/vnd.logik.cfg-v2+json"},
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
  "productId": "01t6e000009bOeLAAU"
}
```

<h3 id="start-configuration-(v2)-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|body|body|[InitConfigV2](#schemainitconfigv2)|true|Initialization Payload|

> Example responses

> 200 Response

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

<h3 id="start-configuration-(v2)-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return the state of configuration at initalization or reconfiguration. Includes fields, messages and products.|[ConfigResponseV2](#schemaconfigresponsev2)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Get Configuration (V2)

<a id="opIdgetConfigByUuidV2"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/vnd.logik.cfg-v2+json',
  'Origin': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://{tenant}.{sector}.logik.io/api/{uuid}', headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'application/vnd.logik.cfg-v2+json',
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
  'Accept':'application/vnd.logik.cfg-v2+json',
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
  -H 'Accept: application/vnd.logik.cfg-v2+json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://{tenant}.{sector}.logik.io/api/{uuid} HTTP/1.1

Accept: application/vnd.logik.cfg-v2+json
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
  'Accept' => 'application/vnd.logik.cfg-v2+json',
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
        "Accept": []string{"application/vnd.logik.cfg-v2+json"},
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

<h3 id="get-configuration-(v2)-parameters">Parameters</h3>

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

<h3 id="get-configuration-(v2)-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return initial state of fields, messages and products|[ConfigResponseV2](#schemaconfigresponsev2)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>

## Update or Save Configuration (V2)

<a id="opIdupdateConfigByUuidV2"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/vnd.logik.cfg-v2+json',
  'Accept': 'application/vnd.logik.cfg-v2+json',
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
      "variableName": "cpuPicker.select",
      "uniqueName": "cpuPicker-1003-cpuPicker.select",
      "value": true,
      "set": "cpuPicker",
      "index": 3
    }
  ]
}';
const headers = {
  'Content-Type':'application/vnd.logik.cfg-v2+json',
  'Accept':'application/vnd.logik.cfg-v2+json',
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
      "variableName": "cpuPicker.select",
      "uniqueName": "cpuPicker-1003-cpuPicker.select",
      "value": true,
      "set": "cpuPicker",
      "index": 3
    }
  ]
};
const headers = {
  'Content-Type':'application/vnd.logik.cfg-v2+json',
  'Accept':'application/vnd.logik.cfg-v2+json',
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
  -H 'Content-Type: application/vnd.logik.cfg-v2+json' \
  -H 'Accept: application/vnd.logik.cfg-v2+json' \
  -H 'Origin: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH https://{tenant}.{sector}.logik.io/api/{uuid} HTTP/1.1

Content-Type: application/vnd.logik.cfg-v2+json
Accept: application/vnd.logik.cfg-v2+json
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
  'Content-Type' => 'application/vnd.logik.cfg-v2+json',
  'Accept' => 'application/vnd.logik.cfg-v2+json',
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
        "Content-Type": []string{"application/vnd.logik.cfg-v2+json"},
        "Accept": []string{"application/vnd.logik.cfg-v2+json"},
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
      "variableName": "cpuPicker.select",
      "uniqueName": "cpuPicker-1003-cpuPicker.select",
      "value": true,
      "set": "cpuPicker",
      "index": 3
    }
  ]
}
```

<h3 id="update-or-save-configuration-(v2)-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Origin|header|string|true|Request Origin, needs to be one of the allowed origins for the Runtime Token being used.|
|uuid|path|string|true|Unique Configuration ID Value|
|delta|query|boolean|false|If `delta=true` the API only retruns changed data. This is default behavior of the API if the parameter is omitted.|
|save|query|boolean|false|Pass `save=true` to save the Configuration and send BOM to connected application|
|body|body|[UpdateConfigV2](#schemaupdateconfigv2)|true|Update or Save Payload for a Configuration.|

> Example responses

> 200 Response

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

<h3 id="update-or-save-configuration-(v2)-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns state of fields, messages and products|[ConfigResponseV2](#schemaconfigresponsev2)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authorization information is missing or invalid.|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Credentials are valid but insufficient privileges to perform the action on the resource.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource was not found. See `errorMessage` for additional details.|[ErrorResponse](#schemaerrorresponse)|
|5XX|Unknown|Unexpected Server Error.|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
RuntimeTokenBearerAuth
</aside>
