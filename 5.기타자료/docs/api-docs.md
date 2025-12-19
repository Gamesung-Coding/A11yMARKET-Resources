---
title: A11yMARKET Server API v0.0.1
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="a11ymarket-server-api">A11yMARKET Server API v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

A11yMARKET Server API Specification Document

Base URLs:

* <a href="http://localhost:8080">http://localhost:8080</a>

# Authentication

- HTTP Authentication, scheme: bearer JWT 토큰을 입력하세요.

<h1 id="a11ymarket-server-api-address-controller">address-controller</h1>

## updateAddress

<a id="opIdupdateAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/v1/users/me/address/{addressId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:8080/api/v1/users/me/address/{addressId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/address/{addressId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:8080/api/v1/users/me/address/{addressId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:8080/api/v1/users/me/address/{addressId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:8080/api/v1/users/me/address/{addressId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/address/{addressId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/api/v1/users/me/address/{addressId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/v1/users/me/address/{addressId}`

> Body parameter

```json
{
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true
}
```

<h3 id="updateaddress-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|addressId|path|string|true|none|
|body|body|[AddressRequest](#schemaaddressrequest)|true|none|

> Example responses

> 200 Response

<h3 id="updateaddress-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AddressResponse](#schemaaddressresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateaddress-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## deleteAddress

<a id="opIddeleteAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/v1/users/me/address/{addressId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://localhost:8080/api/v1/users/me/address/{addressId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/address/{addressId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://localhost:8080/api/v1/users/me/address/{addressId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://localhost:8080/api/v1/users/me/address/{addressId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:8080/api/v1/users/me/address/{addressId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/address/{addressId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/api/v1/users/me/address/{addressId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/v1/users/me/address/{addressId}`

<h3 id="deleteaddress-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|addressId|path|string|true|none|

> Example responses

> 400 Response

<h3 id="deleteaddress-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="deleteaddress-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getAddressList

<a id="opIdgetAddressList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me/address \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me/address HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/address',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me/address',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me/address', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me/address', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/address");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me/address", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me/address`

> Example responses

> 200 Response

<h3 id="getaddresslist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getaddresslist-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[AddressResponse](#schemaaddressresponse)]|false|none|none|
|» addressId|string(uuid)|false|none|none|
|» userId|string(uuid)|false|none|none|
|» addressName|string|false|none|none|
|» receiverName|string|false|none|none|
|» receiverPhone|string|false|none|none|
|» receiverZipcode|string|false|none|none|
|» receiverAddr1|string|false|none|none|
|» receiverAddr2|string|false|none|none|
|» isDefault|boolean|false|none|none|
|» createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## insertAddress

<a id="opIdinsertAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/users/me/address \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/users/me/address HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/address',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/users/me/address',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/users/me/address', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/users/me/address', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/address");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/users/me/address", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/users/me/address`

> Body parameter

```json
{
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true
}
```

<h3 id="insertaddress-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AddressRequest](#schemaaddressrequest)|true|none|

> Example responses

> 201 Response

<h3 id="insertaddress-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[AddressResponse](#schemaaddressresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="insertaddress-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getDefaultAddress

<a id="opIdgetDefaultAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me/default-address \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me/default-address HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/default-address',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me/default-address',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me/default-address', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me/default-address', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/default-address");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me/default-address", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me/default-address`

> Example responses

> 200 Response

<h3 id="getdefaultaddress-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AddressResponse](#schemaaddressresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getdefaultaddress-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateDefaultAddress

<a id="opIdupdateDefaultAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/users/me/default-address \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/users/me/default-address HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "addressId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/default-address',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/users/me/default-address',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/users/me/default-address', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/users/me/default-address', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/default-address");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/users/me/default-address", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/users/me/default-address`

> Body parameter

```json
{
  "addressId": "string"
}
```

<h3 id="updatedefaultaddress-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[DefaultAddressRequest](#schemadefaultaddressrequest)|true|none|

> Example responses

> 200 Response

<h3 id="updatedefaultaddress-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updatedefaultaddress-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-user-a-11y-profile-controller">user-a-11y-profile-controller</h1>

## updateProfile

<a id="opIdupdateProfile"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "profileName": "string",
  "description": "string",
  "contrastLevel": 3,
  "textSizeLevel": 2,
  "textSpacingLevel": 2,
  "lineHeightLevel": 2,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/v1/users/me/a11y/profiles/{profileId}`

> Body parameter

```json
{
  "profileName": "string",
  "description": "string",
  "contrastLevel": 3,
  "textSizeLevel": 2,
  "textSpacingLevel": 2,
  "lineHeightLevel": 2,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true
}
```

<h3 id="updateprofile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|profileId|path|string|true|none|
|body|body|[UserA11yProfileReq](#schemausera11yprofilereq)|true|none|

> Example responses

> 400 Response

<h3 id="updateprofile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateprofile-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## deleteProfile

<a id="opIddeleteProfile"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/api/v1/users/me/a11y/profiles/{profileId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/v1/users/me/a11y/profiles/{profileId}`

<h3 id="deleteprofile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|profileId|path|string|true|none|

> Example responses

> 400 Response

<h3 id="deleteprofile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="deleteprofile-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getMyProfiles

<a id="opIdgetMyProfiles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me/a11y/profiles \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me/a11y/profiles HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/a11y/profiles',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me/a11y/profiles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me/a11y/profiles', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me/a11y/profiles', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/a11y/profiles");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me/a11y/profiles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me/a11y/profiles`

> Example responses

> 200 Response

<h3 id="getmyprofiles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getmyprofiles-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UserA11yProfileResponse](#schemausera11yprofileresponse)]|false|none|none|
|» profileId|string(uuid)|false|none|none|
|» profileName|string|false|none|none|
|» description|string|false|none|none|
|» contrastLevel|integer(int32)|false|none|none|
|» textSizeLevel|integer(int32)|false|none|none|
|» textSpacingLevel|integer(int32)|false|none|none|
|» lineHeightLevel|integer(int32)|false|none|none|
|» textAlign|string|false|none|none|
|» screenReader|boolean|false|none|none|
|» smartContrast|boolean|false|none|none|
|» highlightLinks|boolean|false|none|none|
|» cursorHighlight|boolean|false|none|none|
|» createdAt|string(date-time)|false|none|none|
|» updatedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## createProfile

<a id="opIdcreateProfile"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/users/me/a11y/profiles \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/users/me/a11y/profiles HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "profileName": "string",
  "description": "string",
  "contrastLevel": 3,
  "textSizeLevel": 2,
  "textSpacingLevel": 2,
  "lineHeightLevel": 2,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/a11y/profiles',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/users/me/a11y/profiles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/users/me/a11y/profiles', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/users/me/a11y/profiles', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/a11y/profiles");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/users/me/a11y/profiles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/users/me/a11y/profiles`

> Body parameter

```json
{
  "profileName": "string",
  "description": "string",
  "contrastLevel": 3,
  "textSizeLevel": 2,
  "textSpacingLevel": 2,
  "lineHeightLevel": 2,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true
}
```

<h3 id="createprofile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserA11yProfileReq](#schemausera11yprofilereq)|true|none|

> Example responses

> 200 Response

<h3 id="createprofile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserA11yProfileResponse](#schemausera11yprofileresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="createprofile-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-seller-controller">seller-controller</h1>

## updateProduct

<a id="opIdupdateProduct"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/v1/seller/products/{productId} \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:8080/api/v1/seller/products/{productId} HTTP/1.1
Host: localhost:8080
Content-Type: multipart/form-data
Accept: */*

```

```javascript
const inputBody = '{
  "data": {
    "productName": "string",
    "productDescription": "string",
    "categoryId": "string",
    "productPrice": 0,
    "productStock": 0,
    "productStatus": "PENDING",
    "imageMetadataList": [
      {
        "originalFileName": "string",
        "altText": "string",
        "sequence": 0,
        "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
        "isNew": true
      }
    ]
  },
  "images": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/products/{productId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:8080/api/v1/seller/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:8080/api/v1/seller/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:8080/api/v1/seller/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/products/{productId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/api/v1/seller/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/v1/seller/products/{productId}`

> Body parameter

```yaml
data:
  productName: string
  productDescription: string
  categoryId: string
  productPrice: 0
  productStock: 0
  productStatus: PENDING
  imageMetadataList:
    - originalFileName: string
      altText: string
      sequence: 0
      imageId: bbefe473-c66a-4040-85cf-1c7e6f0b3830
      isNew: true
images:
  - string

```

<h3 id="updateproduct-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|none|
|body|body|object|false|none|
|» data|body|[SellerProductUpdateRequest](#schemasellerproductupdaterequest)|true|Product registration data|
|»» productName|body|string|true|none|
|»» productDescription|body|string|true|none|
|»» categoryId|body|string|true|none|
|»» productPrice|body|integer(int32)|true|none|
|»» productStock|body|integer(int32)|true|none|
|»» productStatus|body|string|false|none|
|»» imageMetadataList|body|[[ImageMetadata](#schemaimagemetadata)]|false|none|
|»»» originalFileName|body|string|true|none|
|»»» altText|body|string|false|none|
|»»» sequence|body|integer(int32)|true|none|
|»»» imageId|body|string(uuid)|false|none|
|»»» isNew|body|boolean|false|none|
|» images|body|[string]|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» productStatus|PENDING|
|»» productStatus|APPROVED|
|»» productStatus|REJECTED|
|»» productStatus|PAUSED|
|»» productStatus|DELETED|

> Example responses

> 200 Response

<h3 id="updateproduct-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ProductDTO](#schemaproductdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateproduct-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## deleteProduct

<a id="opIddeleteProduct"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/v1/seller/products/{productId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://localhost:8080/api/v1/seller/products/{productId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/products/{productId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://localhost:8080/api/v1/seller/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://localhost:8080/api/v1/seller/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:8080/api/v1/seller/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/products/{productId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/api/v1/seller/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/v1/seller/products/{productId}`

<h3 id="deleteproduct-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|none|

> Example responses

> 400 Response

<h3 id="deleteproduct-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="deleteproduct-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateSellerInfo

<a id="opIdupdateSellerInfo"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/v1/seller/me \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:8080/api/v1/seller/me HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "sellerName": "string",
  "sellerIntro": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/me',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:8080/api/v1/seller/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:8080/api/v1/seller/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:8080/api/v1/seller/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/me");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/api/v1/seller/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/v1/seller/me`

> Body parameter

```json
{
  "sellerName": "string",
  "sellerIntro": "string"
}
```

<h3 id="updatesellerinfo-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SellerUpdateRequest](#schemasellerupdaterequest)|true|none|

> Example responses

> 200 Response

<h3 id="updatesellerinfo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerInfoResponse](#schemasellerinforesponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updatesellerinfo-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getMyProducts

<a id="opIdgetMyProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/products?req=page,0,size,0 \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/products?req=page,0,size,0 HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/products?req=page,0,size,0',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/products',
  params: {
  'req' => '[SellerInquireProductRequest](#schemasellerinquireproductrequest)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/products', params={
  'req': {
  "page": 0,
  "size": 0
}
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/products?req=page,0,size,0");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/products`

<h3 id="getmyproducts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|req|query|[SellerInquireProductRequest](#schemasellerinquireproductrequest)|true|none|

> Example responses

> 200 Response

<h3 id="getmyproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getmyproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ProductInquireResponse](#schemaproductinquireresponse)]|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productStock|integer(int32)|false|none|none|
|» productStatus|string|false|none|none|
|» categoryName|string|false|none|none|
|» approvedAt|string(date-time)|false|none|none|
|» updatedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## registerProduct

<a id="opIdregisterProduct"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/seller/products \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/seller/products HTTP/1.1
Host: localhost:8080
Content-Type: multipart/form-data
Accept: */*

```

```javascript
const inputBody = '{
  "data": {
    "productName": "string",
    "productDescription": "string",
    "categoryId": "string",
    "productPrice": 0,
    "productStock": 0,
    "imageMetadataList": [
      {
        "originalFileName": "string",
        "altText": "string",
        "sequence": 0,
        "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
        "isNew": true
      }
    ]
  },
  "images": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/products',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/seller/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/seller/products', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/seller/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/products");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/seller/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/seller/products`

> Body parameter

```yaml
data:
  productName: string
  productDescription: string
  categoryId: string
  productPrice: 0
  productStock: 0
  imageMetadataList:
    - originalFileName: string
      altText: string
      sequence: 0
      imageId: bbefe473-c66a-4040-85cf-1c7e6f0b3830
      isNew: true
images:
  - string

```

<h3 id="registerproduct-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» data|body|[SellerProductRegisterRequest](#schemasellerproductregisterrequest)|true|Product registration data|
|»» productName|body|string|true|none|
|»» productDescription|body|string|true|none|
|»» categoryId|body|string|true|none|
|»» productPrice|body|integer(int32)|true|none|
|»» productStock|body|integer(int32)|true|none|
|»» imageMetadataList|body|[[ImageMetadata](#schemaimagemetadata)]|false|none|
|»»» originalFileName|body|string|true|none|
|»»» altText|body|string|false|none|
|»»» sequence|body|integer(int32)|true|none|
|»»» imageId|body|string(uuid)|false|none|
|»»» isNew|body|boolean|false|none|
|» images|body|[string]|false|none|

> Example responses

> 201 Response

<h3 id="registerproduct-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[ProductDetailResponse](#schemaproductdetailresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="registerproduct-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## processOrderClaim

<a id="opIdprocessOrderClaim"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/seller/claims/{claimId}/approve \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/seller/claims/{claimId}/approve HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "action": "APPROVED"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/claims/{claimId}/approve',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/seller/claims/{claimId}/approve',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/seller/claims/{claimId}/approve', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/seller/claims/{claimId}/approve', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/claims/{claimId}/approve");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/seller/claims/{claimId}/approve", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/seller/claims/{claimId}/approve`

> Body parameter

```json
{
  "action": "APPROVED"
}
```

<h3 id="processorderclaim-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|claimId|path|string|true|none|
|body|body|[SellerOrderClaimProcessRequest](#schemasellerorderclaimprocessrequest)|true|none|

> Example responses

> 400 Response

<h3 id="processorderclaim-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="processorderclaim-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## applySeller

<a id="opIdapplySeller"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/seller/apply \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/seller/apply HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerIntro": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/apply',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/seller/apply',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/seller/apply', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/seller/apply', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/apply");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/seller/apply", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/seller/apply`

> Body parameter

```json
{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerIntro": "string"
}
```

<h3 id="applyseller-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SellerApplyRequest](#schemasellerapplyrequest)|true|none|

> Example responses

> 201 Response

<h3 id="applyseller-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[SellerApplyResponse](#schemasellerapplyresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="applyseller-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateProductStock

<a id="opIdupdateProductStock"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/seller/products/{productId}/stock \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/seller/products/{productId}/stock HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "productStock": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/products/{productId}/stock',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/seller/products/{productId}/stock',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/seller/products/{productId}/stock', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/seller/products/{productId}/stock', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/products/{productId}/stock");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/seller/products/{productId}/stock", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/seller/products/{productId}/stock`

> Body parameter

```json
{
  "productStock": 0
}
```

<h3 id="updateproductstock-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|none|
|body|body|[SellerProductStockUpdateRequest](#schemasellerproductstockupdaterequest)|true|none|

> Example responses

> 200 Response

<h3 id="updateproductstock-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ProductDTO](#schemaproductdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateproductstock-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateOrderStatus

<a id="opIdupdateOrderStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "status": "ORDERED"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/seller/orders/items/{orderItemId}/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/seller/orders/items/{orderItemId}/status`

> Body parameter

```json
{
  "status": "ORDERED"
}
```

<h3 id="updateorderstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderItemId|path|string|true|none|
|body|body|[SellerOrderItemsStatusUpdateRequest](#schemasellerorderitemsstatusupdaterequest)|true|none|

> Example responses

> 400 Response

<h3 id="updateorderstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateorderstatus-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getOrderSummary

<a id="opIdgetOrderSummary"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/orders/summary \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/orders/summary HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/orders/summary',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/orders/summary',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/orders/summary', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/orders/summary', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/orders/summary");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/orders/summary", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/orders/summary`

> Example responses

> 200 Response

<h3 id="getordersummary-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerOrderSummaryResponse](#schemasellerordersummaryresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getordersummary-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getReceivedOrders

<a id="opIdgetReceivedOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/orders/items \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/orders/items HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/orders/items',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/orders/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/orders/items', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/orders/items', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/orders/items");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/orders/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/orders/items`

<h3 id="getreceivedorders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer(int32)|false|none|
|size|query|integer(int32)|false|none|
|orderItemStatus|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

> Example responses

> 200 Response

<h3 id="getreceivedorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerOrderInquireResponse](#schemasellerorderinquireresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getreceivedorders-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getSellerInfo

<a id="opIdgetSellerInfo"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/info/{sellerId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/info/{sellerId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/info/{sellerId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/info/{sellerId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/info/{sellerId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/info/{sellerId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/info/{sellerId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/info/{sellerId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/info/{sellerId}`

<h3 id="getsellerinfo-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sellerId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getsellerinfo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerInfoResponse](#schemasellerinforesponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getsellerinfo-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getTopProducts

<a id="opIdgetTopProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/dashboard/top-products?topN=0 \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/dashboard/top-products?topN=0 HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/dashboard/top-products?topN=0',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/dashboard/top-products',
  params: {
  'topN' => 'integer(int32)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/dashboard/top-products', params={
  'topN': '0'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/dashboard/top-products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/dashboard/top-products?topN=0");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/dashboard/top-products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/dashboard/top-products`

<h3 id="gettopproducts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|topN|query|integer(int32)|true|none|

> Example responses

> 200 Response

<h3 id="gettopproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="gettopproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SellerTopProductResponse](#schemasellertopproductresponse)]|false|none|none|
|» sellerId|string(uuid)|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productImageUrl|string|false|none|none|
|» orderCount|integer(int64)|false|none|none|
|» totalQuantitySold|integer(int64)|false|none|none|
|» totalSalesAmount|number|false|none|none|
|» salesRank|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getDashboardStats

<a id="opIdgetDashboardStats"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/dashboard/stats \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/dashboard/stats HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/dashboard/stats',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/dashboard/stats',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/dashboard/stats', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/dashboard/stats', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/dashboard/stats");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/dashboard/stats", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/dashboard/stats`

> Example responses

> 200 Response

<h3 id="getdashboardstats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerDashboardResponse](#schemasellerdashboardresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getdashboardstats-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getRecentOrders

<a id="opIdgetRecentOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/dashboard/recent-orders \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/dashboard/recent-orders HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/dashboard/recent-orders',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/dashboard/recent-orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/dashboard/recent-orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/dashboard/recent-orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/dashboard/recent-orders");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/dashboard/recent-orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/dashboard/recent-orders`

<h3 id="getrecentorders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer(int32)|false|none|
|size|query|integer(int32)|false|none|

> Example responses

> 200 Response

<h3 id="getrecentorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getrecentorders-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SellerOrderItemResponse](#schemasellerorderitemresponse)]|false|none|none|
|» orderItemId|string(uuid)|false|none|none|
|» orderId|string(uuid)|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productQuantity|integer(int32)|false|none|none|
|» orderItemStatus|string|false|none|none|
|» buyerName|string|false|none|none|
|» buyerEmail|string|false|none|none|
|» buyerPhone|string|false|none|none|
|» orderedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getDailyRevenue

<a id="opIdgetDailyRevenue"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/dashboard/daily-revenue \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/dashboard/daily-revenue HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/dashboard/daily-revenue',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/dashboard/daily-revenue',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/dashboard/daily-revenue', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/dashboard/daily-revenue', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/dashboard/daily-revenue");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/dashboard/daily-revenue", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/dashboard/daily-revenue`

<h3 id="getdailyrevenue-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|year|query|integer(int32)|false|none|
|month|query|integer(int32)|false|none|

> Example responses

> 200 Response

<h3 id="getdailyrevenue-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getdailyrevenue-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[DailyRevenueDto](#schemadailyrevenuedto)]|false|none|none|
|» orderDate|string(date-time)|false|none|none|
|» dailyRevenue|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getOrderClaims

<a id="opIdgetOrderClaims"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/seller/claims \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/seller/claims HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/seller/claims',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/seller/claims',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/seller/claims', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/seller/claims', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/seller/claims");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/seller/claims", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/seller/claims`

> Example responses

> 200 Response

<h3 id="getorderclaims-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getorderclaims-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SellerOrderItemResponse](#schemasellerorderitemresponse)]|false|none|none|
|» orderItemId|string(uuid)|false|none|none|
|» orderId|string(uuid)|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productQuantity|integer(int32)|false|none|none|
|» orderItemStatus|string|false|none|none|
|» buyerName|string|false|none|none|
|» buyerEmail|string|false|none|none|
|» buyerPhone|string|false|none|none|
|» orderedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-order-controller">order-controller</h1>

## getOrderSheet

<a id="opIdgetOrderSheet"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v2/orders/pre-check \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v2/orders/pre-check HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v2/orders/pre-check',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v2/orders/pre-check',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v2/orders/pre-check', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v2/orders/pre-check', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v2/orders/pre-check");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v2/orders/pre-check", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v2/orders/pre-check`

> Body parameter

```json
{
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}
```

<h3 id="getordersheet-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderSheetRequest](#schemaordersheetrequest)|true|none|

> Example responses

> 200 Response

<h3 id="getordersheet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderSheetResponse](#schemaordersheetresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getordersheet-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## confirmOrderItems

<a id="opIdconfirmOrderItems"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/users/me/orders/items/confirm \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/users/me/orders/items/confirm HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "orderItemId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/orders/items/confirm',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/users/me/orders/items/confirm',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/users/me/orders/items/confirm', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/users/me/orders/items/confirm', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/orders/items/confirm");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/users/me/orders/items/confirm", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/users/me/orders/items/confirm`

> Body parameter

```json
{
  "orderItemId": "string"
}
```

<h3 id="confirmorderitems-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderConfirmRequest](#schemaorderconfirmrequest)|true|none|

> Example responses

> 400 Response

<h3 id="confirmorderitems-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="confirmorderitems-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## cancelOrderItems

<a id="opIdcancelOrderItems"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/users/me/orders/cancel-request \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/users/me/orders/cancel-request HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "orderItemId": "string",
  "reason": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/orders/cancel-request',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/users/me/orders/cancel-request',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/users/me/orders/cancel-request', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/users/me/orders/cancel-request', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/orders/cancel-request");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/users/me/orders/cancel-request", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/users/me/orders/cancel-request`

> Body parameter

```json
{
  "orderItemId": "string",
  "reason": "string"
}
```

<h3 id="cancelorderitems-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCancelRequest](#schemaordercancelrequest)|true|none|

> Example responses

> 204 Response

<h3 id="cancelorderitems-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="cancelorderitems-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## verifyPayment

<a id="opIdverifyPayment"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/payments/verify \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/payments/verify HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "orderId": "string",
  "amount": 0,
  "method": "string",
  "paymentKey": "string",
  "impUid": "string",
  "cartItemIdsToDelete": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/payments/verify',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/payments/verify',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/payments/verify', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/payments/verify', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/payments/verify");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/payments/verify", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/payments/verify`

> Body parameter

```json
{
  "orderId": "string",
  "amount": 0,
  "method": "string",
  "paymentKey": "string",
  "impUid": "string",
  "cartItemIdsToDelete": [
    "string"
  ]
}
```

<h3 id="verifypayment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaymentVerifyRequest](#schemapaymentverifyrequest)|true|none|

> Example responses

> 200 Response

<h3 id="verifypayment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PaymentVerifyResponse](#schemapaymentverifyresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="verifypayment-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## createOrder

<a id="opIdcreateOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/orders HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "addressId": "string",
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/orders',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/orders");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/orders`

> Body parameter

```json
{
  "addressId": "string",
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}
```

<h3 id="createorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCreateRequest](#schemaordercreaterequest)|true|none|

> Example responses

> 201 Response

<h3 id="createorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[OrderResponse](#schemaorderresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="createorder-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## preCheck

<a id="opIdpreCheck"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/orders/pre-check \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/orders/pre-check HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/orders/pre-check',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/orders/pre-check',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/orders/pre-check', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/orders/pre-check', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/orders/pre-check");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/orders/pre-check", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/orders/pre-check`

> Example responses

> 400 Response

<h3 id="precheck-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="precheck-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getMyOrders

<a id="opIdgetMyOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me/orders \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me/orders HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/orders',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me/orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/orders");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me/orders`

> Example responses

> 200 Response

<h3 id="getmyorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getmyorders-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[OrderResponse](#schemaorderresponse)]|false|none|none|
|» orderId|string(uuid)|false|none|none|
|» totalPrice|integer(int32)|false|none|none|
|» orderItems|[[OrderItemResponse](#schemaorderitemresponse)]|false|none|none|
|»» orderItemId|string(uuid)|false|none|none|
|»» productId|string(uuid)|false|none|none|
|»» productName|string|false|none|none|
|»» categoryName|string|false|none|none|
|»» productPrice|integer(int32)|false|none|none|
|»» productQuantity|integer(int32)|false|none|none|
|»» productTotalPrice|integer(int32)|false|none|none|
|»» productImageUrl|string|false|none|none|
|»» orderItemStatus|string|false|none|none|
|»» cancelReason|string|false|none|none|
|» createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getMyOrderDetail

<a id="opIdgetMyOrderDetail"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me/orders/{orderItemId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me/orders/{orderItemId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me/orders/{orderItemId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me/orders/{orderItemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me/orders/{orderItemId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me/orders/{orderItemId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me/orders/{orderItemId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me/orders/{orderItemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me/orders/{orderItemId}`

<h3 id="getmyorderdetail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderItemId|path|string(uuid)|true|none|

> Example responses

> 200 Response

<h3 id="getmyorderdetail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderDetailResponse](#schemaorderdetailresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getmyorderdetail-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-cart-controller">cart-controller</h1>

## addItem

<a id="opIdaddItem"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/cart/me/items \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/cart/me/items HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "productId": "string",
  "quantity": 1
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/cart/me/items',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/cart/me/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/cart/me/items', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/cart/me/items', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/cart/me/items");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/cart/me/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/cart/me/items`

> Body parameter

```json
{
  "productId": "string",
  "quantity": 1
}
```

<h3 id="additem-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CartAddRequest](#schemacartaddrequest)|true|none|

> Example responses

> 201 Response

<h3 id="additem-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[CartItemUpdatedResponse](#schemacartitemupdatedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="additem-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## deleteItems

<a id="opIddeleteItems"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/v1/cart/me/items \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://localhost:8080/api/v1/cart/me/items HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "itemIds": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/cart/me/items',
{
  method: 'DELETE',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://localhost:8080/api/v1/cart/me/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://localhost:8080/api/v1/cart/me/items', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:8080/api/v1/cart/me/items', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/cart/me/items");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/api/v1/cart/me/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/v1/cart/me/items`

> Body parameter

```json
{
  "itemIds": [
    "string"
  ]
}
```

<h3 id="deleteitems-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CartItemDeleteRequest](#schemacartitemdeleterequest)|true|none|

> Example responses

> 400 Response

<h3 id="deleteitems-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="deleteitems-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateQuantity

<a id="opIdupdateQuantity"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/cart/me/items/{cartItemId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/cart/me/items/{cartItemId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "quantity": 1
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/cart/me/items/{cartItemId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/cart/me/items/{cartItemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/cart/me/items/{cartItemId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/cart/me/items/{cartItemId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/cart/me/items/{cartItemId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/cart/me/items/{cartItemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/cart/me/items/{cartItemId}`

> Body parameter

```json
{
  "quantity": 1
}
```

<h3 id="updatequantity-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cartItemId|path|string|true|none|
|body|body|[CartQtyUpdateRequest](#schemacartqtyupdaterequest)|true|none|

> Example responses

> 200 Response

<h3 id="updatequantity-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CartItemUpdatedResponse](#schemacartitemupdatedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updatequantity-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getCart

<a id="opIdgetCart"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/cart/me \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/cart/me HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/cart/me',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/cart/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/cart/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/cart/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/cart/me");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/cart/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/cart/me`

> Example responses

> 200 Response

<h3 id="getcart-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CartItemListResponse](#schemacartitemlistresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getcart-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getCartItemCount

<a id="opIdgetCartItemCount"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/cart/me/items/count \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/cart/me/items/count HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/cart/me/items/count',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/cart/me/items/count',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/cart/me/items/count', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/cart/me/items/count', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/cart/me/items/count");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/cart/me/items/count", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/cart/me/items/count`

> Example responses

> 200 Response

<h3 id="getcartitemcount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CartItemCountResponse](#schemacartitemcountresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getcartitemcount-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-auth-controller">auth-controller</h1>

## refreshToken

<a id="opIdrefreshToken"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/refresh \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/refresh HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "refreshToken": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/refresh',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/refresh',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/refresh', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/refresh', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/refresh");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/refresh", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/refresh`

> Body parameter

```json
{
  "refreshToken": "string"
}
```

<h3 id="refreshtoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RefreshRequest](#schemarefreshrequest)|true|none|

> Example responses

> 200 Response

<h3 id="refreshtoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[JwtResponse](#schemajwtresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="refreshtoken-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## logout

<a id="opIdlogout"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/logout \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/logout HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/logout',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/logout',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/logout', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/logout', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/logout");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/logout", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/logout`

> Example responses

> 204 Response

<h3 id="logout-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="logout-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## login

<a id="opIdlogin"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/login \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/login HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "email": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/login',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/login',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/login', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/login', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/login");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/login", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/login`

> Body parameter

```json
{
  "email": "string",
  "password": "string"
}
```

<h3 id="login-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LoginRequest](#schemaloginrequest)|true|none|

> Example responses

> 200 Response

<h3 id="login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LoginResponse](#schemaloginresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="login-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## loginRefresh

<a id="opIdloginRefresh"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/login-refresh \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/login-refresh HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "refreshToken": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/login-refresh',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/login-refresh',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/login-refresh', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/login-refresh', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/login-refresh");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/login-refresh", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/login-refresh`

> Body parameter

```json
{
  "refreshToken": "string"
}
```

<h3 id="loginrefresh-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RefreshRequest](#schemarefreshrequest)|true|none|

> Example responses

> 200 Response

<h3 id="loginrefresh-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LoginResponse](#schemaloginresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="loginrefresh-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## kakaoJoin

<a id="opIdkakaoJoin"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/kakao-join \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/kakao-join HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "userEmail": "string",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/kakao-join',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/kakao-join',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/kakao-join', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/kakao-join', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/kakao-join");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/kakao-join", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/kakao-join`

> Body parameter

```json
{
  "userEmail": "string",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}
```

<h3 id="kakaojoin-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[KakaoSignUpRequest](#schemakakaosignuprequest)|true|none|

> Example responses

> 201 Response

<h3 id="kakaojoin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="kakaojoin-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## join

<a id="opIdjoin"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/v1/auth/join \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:8080/api/v1/auth/join HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "userEmail": "string",
  "userPass": "stringst",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/join',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:8080/api/v1/auth/join',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:8080/api/v1/auth/join', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:8080/api/v1/auth/join', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/join");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/api/v1/auth/join", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/v1/auth/join`

> Body parameter

```json
{
  "userEmail": "string",
  "userPass": "stringst",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}
```

<h3 id="join-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[JoinRequest](#schemajoinrequest)|true|none|

> Example responses

> 201 Response

<h3 id="join-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="join-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getLoginUserInfo

<a id="opIdgetLoginUserInfo"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/auth/me/info \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/auth/me/info HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/me/info',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/auth/me/info',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/auth/me/info', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/auth/me/info', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/me/info");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/auth/me/info", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/auth/me/info`

> Example responses

> 200 Response

<h3 id="getloginuserinfo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LoginResponse](#schemaloginresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getloginuserinfo-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## checkPhone

<a id="opIdcheckPhone"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/auth/check/phone?phone=string \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/auth/check/phone?phone=string HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/check/phone?phone=string',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/auth/check/phone',
  params: {
  'phone' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/auth/check/phone', params={
  'phone': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/auth/check/phone', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/check/phone?phone=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/auth/check/phone", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/auth/check/phone`

<h3 id="checkphone-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|phone|query|string|true|none|

> Example responses

> 200 Response

<h3 id="checkphone-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CheckExistsResponse](#schemacheckexistsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="checkphone-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## checkNickname

<a id="opIdcheckNickname"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/auth/check/nickname?nickname=string \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/auth/check/nickname?nickname=string HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/check/nickname?nickname=string',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/auth/check/nickname',
  params: {
  'nickname' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/auth/check/nickname', params={
  'nickname': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/auth/check/nickname', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/check/nickname?nickname=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/auth/check/nickname", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/auth/check/nickname`

<h3 id="checknickname-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|nickname|query|string|true|none|

> Example responses

> 200 Response

<h3 id="checknickname-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CheckExistsResponse](#schemacheckexistsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="checknickname-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## checkEmail

<a id="opIdcheckEmail"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/auth/check/email?email=string \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/auth/check/email?email=string HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/auth/check/email?email=string',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/auth/check/email',
  params: {
  'email' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/auth/check/email', params={
  'email': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/auth/check/email', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/auth/check/email?email=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/auth/check/email", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/auth/check/email`

<h3 id="checkemail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|email|query|string|true|none|

> Example responses

> 200 Response

<h3 id="checkemail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CheckExistsResponse](#schemacheckexistsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="checkemail-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-user-controller">user-controller</h1>

## getUserInfo

<a id="opIdgetUserInfo"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/users/me \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/users/me HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/users/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/users/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/users/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/users/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/users/me`

> Example responses

> 200 Response

<h3 id="getuserinfo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getuserinfo-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## deleteUser

<a id="opIddeleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/v1/users/me \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://localhost:8080/api/v1/users/me HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "userPassword": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me',
{
  method: 'DELETE',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://localhost:8080/api/v1/users/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://localhost:8080/api/v1/users/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:8080/api/v1/users/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/api/v1/users/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/v1/users/me`

> Body parameter

```json
{
  "userPassword": "string"
}
```

<h3 id="deleteuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserDeleteRequest](#schemauserdeleterequest)|true|none|

> Example responses

> 400 Response

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="deleteuser-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateUserInfo

<a id="opIdupdateUserInfo"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/users/me \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/users/me HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "userNickname": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/users/me',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/users/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/users/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/users/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/users/me");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/users/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/users/me`

> Body parameter

```json
{
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "userNickname": "string"
}
```

<h3 id="updateuserinfo-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserUpdateRequest](#schemauserupdaterequest)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserinfo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updateuserinfo-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-admin-user-manage-controller">admin-user-manage-controller</h1>

## changeUserPermission

<a id="opIdchangeUserPermission"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/admin/users/{userId}/permission?role=USER \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/admin/users/{userId}/permission?role=USER HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/users/{userId}/permission?role=USER',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/admin/users/{userId}/permission',
  params: {
  'role' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/admin/users/{userId}/permission', params={
  'role': 'USER'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/admin/users/{userId}/permission', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/users/{userId}/permission?role=USER");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/admin/users/{userId}/permission", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/admin/users/{userId}/permission`

<h3 id="changeuserpermission-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|
|role|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|role|USER|
|role|SELLER|
|role|ADMIN|
|role|TEMP|

> Example responses

> 200 Response

<h3 id="changeuserpermission-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponse](#schemauserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="changeuserpermission-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquireUsers

<a id="opIdinquireUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/users \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/users HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/users',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/users");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/users`

> Example responses

> 200 Response

<h3 id="inquireusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquireusers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UserAdminResponse](#schemauseradminresponse)]|false|none|none|
|» userId|string(uuid)|false|none|none|
|» userName|string|false|none|none|
|» userEmail|string|false|none|none|
|» userNickname|string|false|none|none|
|» userRole|string|false|none|none|
|» createdAt|string(date-time)|false|none|none|
|» updatedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userRole|USER|
|userRole|SELLER|
|userRole|ADMIN|
|userRole|TEMP|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-admin-seller-manage-controller">admin-seller-manage-controller</h1>

## getSellerProfile

<a id="opIdgetSellerProfile"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/sellers/{sellerId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/sellers/{sellerId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/sellers/{sellerId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/sellers/{sellerId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/sellers/{sellerId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/sellers/{sellerId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/sellers/{sellerId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/sellers/{sellerId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/sellers/{sellerId}`

<h3 id="getsellerprofile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sellerId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getsellerprofile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SellerDetailResponse](#schemasellerdetailresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getsellerprofile-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## updateSellerInfo_1

<a id="opIdupdateSellerInfo_1"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/admin/sellers/{sellerId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/admin/sellers/{sellerId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
const inputBody = '{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "sellerIntro": "string",
  "a11yGuarantee": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/sellers/{sellerId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/admin/sellers/{sellerId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/admin/sellers/{sellerId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/admin/sellers/{sellerId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/sellers/{sellerId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/admin/sellers/{sellerId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/admin/sellers/{sellerId}`

> Body parameter

```json
{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "sellerIntro": "string",
  "a11yGuarantee": true
}
```

<h3 id="updatesellerinfo_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sellerId|path|string|true|none|
|body|body|[AdminSellerUpdateRequest](#schemaadminsellerupdaterequest)|true|none|

> Example responses

> 204 Response

<h3 id="updatesellerinfo_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="updatesellerinfo_1-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## changeSellerStatus

<a id="opIdchangeSellerStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/admin/sellers/{sellerId}/status?status=PENDING \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/admin/sellers/{sellerId}/status?status=PENDING HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/sellers/{sellerId}/status?status=PENDING',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/admin/sellers/{sellerId}/status',
  params: {
  'status' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/admin/sellers/{sellerId}/status', params={
  'status': 'PENDING'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/admin/sellers/{sellerId}/status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/sellers/{sellerId}/status?status=PENDING");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/admin/sellers/{sellerId}/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/admin/sellers/{sellerId}/status`

<h3 id="changesellerstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sellerId|path|string|true|none|
|status|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|PENDING|
|status|APPROVED|
|status|REJECTED|

> Example responses

> 204 Response

<h3 id="changesellerstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="changesellerstatus-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getAllSellerProfiles

<a id="opIdgetAllSellerProfiles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/sellers \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/sellers HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/sellers',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/sellers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/sellers', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/sellers', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/sellers");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/sellers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/sellers`

> Example responses

> 200 Response

<h3 id="getallsellerprofiles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getallsellerprofiles-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SellerProfileResponse](#schemasellerprofileresponse)]|false|none|none|
|» sellerId|string(uuid)|false|none|none|
|» sellerName|string|false|none|none|
|» businessNumber|string|false|none|none|
|» sellerGrade|string|false|none|none|
|» contactEmail|string|false|none|none|
|» contactPhone|string|false|none|none|
|» storeIntro|string|false|none|none|
|» isA11yGuarantee|boolean|false|none|none|
|» profileStatus|string|false|none|none|
|» submitDate|string(date-time)|false|none|none|
|» approvedDate|string(date-time)|false|none|none|
|» lastUpdatedDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|profileStatus|PENDING|
|profileStatus|APPROVED|
|profileStatus|REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquirePendingSellers

<a id="opIdinquirePendingSellers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/sellers/pending \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/sellers/pending HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/sellers/pending',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/sellers/pending',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/sellers/pending', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/sellers/pending', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/sellers/pending");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/sellers/pending", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/sellers/pending`

> Example responses

> 200 Response

<h3 id="inquirependingsellers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquirependingsellers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SellerApplyResponse](#schemasellerapplyresponse)]|false|none|none|
|» sellerId|string(uuid)|false|none|none|
|» sellerName|string|false|none|none|
|» userName|string|false|none|none|
|» userEmail|string|false|none|none|
|» userPhone|string|false|none|none|
|» businessNumber|string|false|none|none|
|» sellerGrade|string|false|none|none|
|» sellerIntro|string|false|none|none|
|» a11yGuarantee|boolean|false|none|none|
|» sellerSubmitStatus|string|false|none|none|
|» submitDate|string(date-time)|false|none|none|
|» approvedDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|sellerSubmitStatus|PENDING|
|sellerSubmitStatus|APPROVED|
|sellerSubmitStatus|REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-admin-product-manage-controller">admin-product-manage-controller</h1>

## changeProductStatus

<a id="opIdchangeProductStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/admin/products/{productId}/status?status=PENDING \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/admin/products/{productId}/status?status=PENDING HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/products/{productId}/status?status=PENDING',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/admin/products/{productId}/status',
  params: {
  'status' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/admin/products/{productId}/status', params={
  'status': 'PENDING'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/admin/products/{productId}/status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/products/{productId}/status?status=PENDING");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/admin/products/{productId}/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/admin/products/{productId}/status`

<h3 id="changeproductstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|none|
|status|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|PENDING|
|status|APPROVED|
|status|REJECTED|
|status|PAUSED|
|status|DELETED|

> Example responses

> 200 Response

<h3 id="changeproductstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="changeproductstatus-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquireAllProducts

<a id="opIdinquireAllProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/products \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/products HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/products',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/products', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/products");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/products`

<h3 id="inquireallproducts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|none|
|status|query|string|false|none|
|page|query|integer(int32)|false|none|
|size|query|integer(int32)|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|PENDING|
|status|APPROVED|
|status|REJECTED|
|status|PAUSED|
|status|DELETED|

> Example responses

> 200 Response

<h3 id="inquireallproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminProductsResponse](#schemaadminproductsresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquireallproducts-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquirePendingProducts

<a id="opIdinquirePendingProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/products/pending \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/products/pending HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/products/pending',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/products/pending',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/products/pending', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/products/pending', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/products/pending");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/products/pending", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/products/pending`

> Example responses

> 200 Response

<h3 id="inquirependingproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquirependingproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ProductAdminInquireResponse](#schemaproductadmininquireresponse)]|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» sellerId|string(uuid)|false|none|none|
|» sellerName|string|false|none|none|
|» sellerGrade|string|false|none|none|
|» isA11yGuarantee|boolean|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productStatus|string|false|none|none|
|» productDescription|string|false|none|none|
|» productStock|integer(int32)|false|none|none|
|» categoryId|string(uuid)|false|none|none|
|» categoryName|string|false|none|none|
|» submitDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-admin-order-manage-controller">admin-order-manage-controller</h1>

## changeOrderStatus

<a id="opIdchangeOrderStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/v1/admin/orders/items/{orderItemId}?status=ORDERED \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH http://localhost:8080/api/v1/admin/orders/items/{orderItemId}?status=ORDERED HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/orders/items/{orderItemId}?status=ORDERED',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch 'http://localhost:8080/api/v1/admin/orders/items/{orderItemId}',
  params: {
  'status' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('http://localhost:8080/api/v1/admin/orders/items/{orderItemId}', params={
  'status': 'ORDERED'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:8080/api/v1/admin/orders/items/{orderItemId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/orders/items/{orderItemId}?status=ORDERED");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:8080/api/v1/admin/orders/items/{orderItemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/v1/admin/orders/items/{orderItemId}`

<h3 id="changeorderstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderItemId|path|string|true|none|
|status|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|ORDERED|
|status|PAID|
|status|REJECTED|
|status|ACCEPTED|
|status|SHIPPING|
|status|SHIPPED|
|status|CONFIRMED|
|status|CANCEL_PENDING|
|status|CANCELED|
|status|CANCEL_REJECTED|
|status|RETURN_PENDING|
|status|RETURNED|
|status|RETURN_REJECTED|

> Example responses

> 200 Response

<h3 id="changeorderstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="changeorderstatus-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquireAllOrders

<a id="opIdinquireAllOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/orders?request=searchType,string,keyword,string,status,PENDING,startDate,string,endDate,string \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/orders?request=searchType,string,keyword,string,status,PENDING,startDate,string,endDate,string HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/orders?request=searchType,string,keyword,string,status,PENDING,startDate,string,endDate,string',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/orders',
  params: {
  'request' => '[AdminOrderSearchRequest](#schemaadminordersearchrequest)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/orders', params={
  'request': {
  "searchType": "string",
  "keyword": "string",
  "status": "PENDING",
  "startDate": "string",
  "endDate": "string"
}
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/orders?request=searchType,string,keyword,string,status,PENDING,startDate,string,endDate,string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/orders`

<h3 id="inquireallorders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|request|query|[AdminOrderSearchRequest](#schemaadminordersearchrequest)|true|none|

> Example responses

> 200 Response

<h3 id="inquireallorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquireallorders-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[AdminOrderResponse](#schemaadminorderresponse)]|false|none|none|
|» orderId|string(uuid)|false|none|none|
|» userName|string|false|none|none|
|» userEmail|string|false|none|none|
|» userPhone|string|false|none|none|
|» receiverName|string|false|none|none|
|» receiverPhone|string|false|none|none|
|» receiverZipcode|string|false|none|none|
|» receiverAddr1|string|false|none|none|
|» receiverAddr2|string|false|none|none|
|» totalPrice|integer(int32)|false|none|none|
|» items|[[OrderItemResponse](#schemaorderitemresponse)]|false|none|none|
|»» orderItemId|string(uuid)|false|none|none|
|»» productId|string(uuid)|false|none|none|
|»» productName|string|false|none|none|
|»» categoryName|string|false|none|none|
|»» productPrice|integer(int32)|false|none|none|
|»» productQuantity|integer(int32)|false|none|none|
|»» productTotalPrice|integer(int32)|false|none|none|
|»» productImageUrl|string|false|none|none|
|»» orderItemStatus|string|false|none|none|
|»» cancelReason|string|false|none|none|
|» createdAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## inquireOrderDetails

<a id="opIdinquireOrderDetails"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/orders/{orderId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/orders/{orderId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/orders/{orderId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/orders/{orderId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/orders/{orderId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/orders/{orderId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/orders/{orderId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/orders/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/orders/{orderId}`

<h3 id="inquireorderdetails-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="inquireorderdetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderDetailResponse](#schemaorderdetailresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="inquireorderdetails-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-product-controller">product-controller</h1>

## getProducts

<a id="opIdgetProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/products \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/products HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/products',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/products', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/products");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/products`

<h3 id="getproducts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|
|certified|query|boolean|false|none|
|grade|query|string|false|none|
|categoryId|query|array[string]|false|none|

> Example responses

> 200 Response

<h3 id="getproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ProductResponse](#schemaproductresponse)]|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productDescription|string|false|none|none|
|» sellerName|string|false|none|none|
|» isA11yGuarantee|boolean|false|none|none|
|» productPrice|integer(int32)|false|none|none|
|» productImages|[[ProductImageResponse](#schemaproductimageresponse)]|false|none|none|
|»» imageId|string(uuid)|false|none|none|
|»» imageUrl|string|false|none|none|
|»» altText|string|false|none|none|
|»» imageSequence|integer(int32)|false|none|none|
|» parentCategoryId|string(uuid)|false|none|none|
|» categoryId|string(uuid)|false|none|none|
|» categoryName|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getProductDetail

<a id="opIdgetProductDetail"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/products/{productId} \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/products/{productId} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/products/{productId}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/products/{productId}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/products/{productId}`

<h3 id="getproductdetail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getproductdetail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ProductDetailResponse](#schemaproductdetailresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getproductdetail-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-main-controller">main-controller</h1>

## getPopularProducts

<a id="opIdgetPopularProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/main/products/populars \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/main/products/populars HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/main/products/populars',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/main/products/populars',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/main/products/populars', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/main/products/populars', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/main/products/populars");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/main/products/populars", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/main/products/populars`

> Example responses

> 200 Response

<h3 id="getpopularproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getpopularproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[MonthlyPopularProduct](#schemamonthlypopularproduct)]|false|none|none|
|» productId|string(uuid)|false|none|none|
|» productName|string|false|none|none|
|» productPrice|number|false|none|none|
|» productImageUrl|string|false|none|none|
|» categoryId|string(uuid)|false|none|none|
|» categoryName|string|false|none|none|
|» sellerId|string(uuid)|false|none|none|
|» monthlySalesVolume|integer(int64)|false|none|none|
|» monthlyOrderCount|integer(int64)|false|none|none|
|» ranking|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getCategories

<a id="opIdgetCategories"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/main/products/categories \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/main/products/categories HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/main/products/categories',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/main/products/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/main/products/categories', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/main/products/categories', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/main/products/categories");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/main/products/categories", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/main/products/categories`

> Example responses

> 200 Response

<h3 id="getcategories-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getcategories-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[CategoryRecommendResponse](#schemacategoryrecommendresponse)]|false|none|none|
|» categoryId|string(uuid)|false|none|none|
|» categoryName|string|false|none|none|
|» products|[[CatProductInfo](#schemacatproductinfo)]|false|none|none|
|»» productId|string(uuid)|false|none|none|
|»» productName|string|false|none|none|
|»» productPrice|integer(int32)|false|none|none|
|»» productImageUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

## getEvents

<a id="opIdgetEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/main/events \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/main/events HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/main/events',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/main/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/main/events', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/main/events', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/main/events");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/main/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/main/events`

> Example responses

> 200 Response

<h3 id="getevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getevents-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EventResponse](#schemaeventresponse)]|false|none|none|
|» eventTitle|string|false|none|none|
|» eventDescription|string|false|none|none|
|» eventImageUrl|string|false|none|none|
|» eventUrl|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-category-controller">category-controller</h1>

## getAllCategories

<a id="opIdgetAllCategories"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/categories \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/categories HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/categories',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/categories', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/categories', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/categories");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/categories", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/categories`

> Example responses

> 200 Response

<h3 id="getallcategories-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getallcategories-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[CategoryResponse](#schemacategoryresponse)]|false|none|none|
|» categoryId|string(uuid)|false|none|none|
|» categoryName|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

<h1 id="a11ymarket-server-api-admin-dashboard-controller">admin-dashboard-controller</h1>

## getAdminDashboardStats

<a id="opIdgetAdminDashboardStats"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/v1/admin/dashboard/stats \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:8080/api/v1/admin/dashboard/stats HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript

const headers = {
  'Accept':'*/*',
  'Authorization':'Bearer {access-token}'
};

fetch('http://localhost:8080/api/v1/admin/dashboard/stats',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:8080/api/v1/admin/dashboard/stats',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:8080/api/v1/admin/dashboard/stats', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => '*/*',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:8080/api/v1/admin/dashboard/stats', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:8080/api/v1/admin/dashboard/stats");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/api/v1/admin/dashboard/stats", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/v1/admin/dashboard/stats`

> Example responses

> 200 Response

<h3 id="getadmindashboardstats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminDashboardStats](#schemaadmindashboardstats)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[RestErrorResponse](#schemaresterrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Conflict|[RestErrorResponse](#schemaresterrorresponse)|

<h3 id="getadmindashboardstats-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT
</aside>

# Schemas

<h2 id="tocS_LoginErrResponse">LoginErrResponse</h2>
<!-- backwards compatibility -->
<a id="schemaloginerrresponse"></a>
<a id="schema_LoginErrResponse"></a>
<a id="tocSloginerrresponse"></a>
<a id="tocsloginerrresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|

<h2 id="tocS_RestErrorResponse">RestErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaresterrorresponse"></a>
<a id="schema_RestErrorResponse"></a>
<a id="tocSresterrorresponse"></a>
<a id="tocsresterrorresponse"></a>

```json
{
  "status": 0,
  "error": "USER_NOT_FOUND",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|integer(int32)|false|none|none|
|error|string|false|none|none|
|message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|error|USER_NOT_FOUND|
|error|DATA_NOT_FOUND|
|error|DUPLICATED_DATA|
|error|INVALID_REQUEST|

<h2 id="tocS_AddressRequest">AddressRequest</h2>
<!-- backwards compatibility -->
<a id="schemaaddressrequest"></a>
<a id="schema_AddressRequest"></a>
<a id="tocSaddressrequest"></a>
<a id="tocsaddressrequest"></a>

```json
{
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|addressName|string|false|none|none|
|receiverName|string|false|none|none|
|receiverPhone|string|false|none|none|
|receiverZipcode|string|false|none|none|
|receiverAddr1|string|false|none|none|
|receiverAddr2|string|false|none|none|
|isDefault|boolean|false|none|none|

<h2 id="tocS_AddressResponse">AddressResponse</h2>
<!-- backwards compatibility -->
<a id="schemaaddressresponse"></a>
<a id="schema_AddressResponse"></a>
<a id="tocSaddressresponse"></a>
<a id="tocsaddressresponse"></a>

```json
{
  "addressId": "785d1fc4-8ab5-48f1-8685-117cac9865d6",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "addressName": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "isDefault": true,
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|addressId|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|addressName|string|false|none|none|
|receiverName|string|false|none|none|
|receiverPhone|string|false|none|none|
|receiverZipcode|string|false|none|none|
|receiverAddr1|string|false|none|none|
|receiverAddr2|string|false|none|none|
|isDefault|boolean|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_UserA11yProfileReq">UserA11yProfileReq</h2>
<!-- backwards compatibility -->
<a id="schemausera11yprofilereq"></a>
<a id="schema_UserA11yProfileReq"></a>
<a id="tocSusera11yprofilereq"></a>
<a id="tocsusera11yprofilereq"></a>

```json
{
  "profileName": "string",
  "description": "string",
  "contrastLevel": 3,
  "textSizeLevel": 2,
  "textSpacingLevel": 2,
  "lineHeightLevel": 2,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|profileName|string|true|none|none|
|description|string|false|none|none|
|contrastLevel|integer(int32)|false|none|none|
|textSizeLevel|integer(int32)|false|none|none|
|textSpacingLevel|integer(int32)|false|none|none|
|lineHeightLevel|integer(int32)|false|none|none|
|textAlign|string|false|none|none|
|screenReader|boolean|false|none|none|
|smartContrast|boolean|false|none|none|
|highlightLinks|boolean|false|none|none|
|cursorHighlight|boolean|false|none|none|

<h2 id="tocS_ImageMetadata">ImageMetadata</h2>
<!-- backwards compatibility -->
<a id="schemaimagemetadata"></a>
<a id="schema_ImageMetadata"></a>
<a id="tocSimagemetadata"></a>
<a id="tocsimagemetadata"></a>

```json
{
  "originalFileName": "string",
  "altText": "string",
  "sequence": 0,
  "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
  "isNew": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|originalFileName|string|true|none|none|
|altText|string|false|none|none|
|sequence|integer(int32)|true|none|none|
|imageId|string(uuid)|false|none|none|
|isNew|boolean|false|none|none|

<h2 id="tocS_SellerProductUpdateRequest">SellerProductUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerproductupdaterequest"></a>
<a id="schema_SellerProductUpdateRequest"></a>
<a id="tocSsellerproductupdaterequest"></a>
<a id="tocssellerproductupdaterequest"></a>

```json
{
  "productName": "string",
  "productDescription": "string",
  "categoryId": "string",
  "productPrice": 0,
  "productStock": 0,
  "productStatus": "PENDING",
  "imageMetadataList": [
    {
      "originalFileName": "string",
      "altText": "string",
      "sequence": 0,
      "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
      "isNew": true
    }
  ]
}

```

Product registration data

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productName|string|true|none|none|
|productDescription|string|true|none|none|
|categoryId|string|true|none|none|
|productPrice|integer(int32)|true|none|none|
|productStock|integer(int32)|true|none|none|
|productStatus|string|false|none|none|
|imageMetadataList|[[ImageMetadata](#schemaimagemetadata)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

<h2 id="tocS_ProductDTO">ProductDTO</h2>
<!-- backwards compatibility -->
<a id="schemaproductdto"></a>
<a id="schema_ProductDTO"></a>
<a id="tocSproductdto"></a>
<a id="tocsproductdto"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productStatus": "PENDING",
  "submitDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productStatus|string|false|none|none|
|submitDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

<h2 id="tocS_SellerUpdateRequest">SellerUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerupdaterequest"></a>
<a id="schema_SellerUpdateRequest"></a>
<a id="tocSsellerupdaterequest"></a>
<a id="tocssellerupdaterequest"></a>

```json
{
  "sellerName": "string",
  "sellerIntro": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerName|string|true|none|none|
|sellerIntro|string|true|none|none|

<h2 id="tocS_ProductImageResponse">ProductImageResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductimageresponse"></a>
<a id="schema_ProductImageResponse"></a>
<a id="tocSproductimageresponse"></a>
<a id="tocsproductimageresponse"></a>

```json
{
  "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
  "imageUrl": "string",
  "altText": "string",
  "imageSequence": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|imageId|string(uuid)|false|none|none|
|imageUrl|string|false|none|none|
|altText|string|false|none|none|
|imageSequence|integer(int32)|false|none|none|

<h2 id="tocS_ProductResponse">ProductResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductresponse"></a>
<a id="schema_ProductResponse"></a>
<a id="tocSproductresponse"></a>
<a id="tocsproductresponse"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productDescription": "string",
  "sellerName": "string",
  "isA11yGuarantee": true,
  "productPrice": 0,
  "productImages": [
    {
      "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
      "imageUrl": "string",
      "altText": "string",
      "imageSequence": 0
    }
  ],
  "parentCategoryId": "acdf37b5-b785-42a1-be6f-0a9504c832f1",
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productDescription|string|false|none|none|
|sellerName|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productImages|[[ProductImageResponse](#schemaproductimageresponse)]|false|none|none|
|parentCategoryId|string(uuid)|false|none|none|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|

<h2 id="tocS_SellerInfoResponse">SellerInfoResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerinforesponse"></a>
<a id="schema_SellerInfoResponse"></a>
<a id="tocSsellerinforesponse"></a>
<a id="tocssellerinforesponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "businessNumber": "string",
  "sellerIntro": "string",
  "sellerEmail": "string",
  "sellerPhone": "string",
  "isA11yGuarantee": true,
  "sellerGrade": "NEWER",
  "products": [
    {
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "productDescription": "string",
      "sellerName": "string",
      "isA11yGuarantee": true,
      "productPrice": 0,
      "productImages": [
        {
          "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
          "imageUrl": "string",
          "altText": "string",
          "imageSequence": 0
        }
      ],
      "parentCategoryId": "acdf37b5-b785-42a1-be6f-0a9504c832f1",
      "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
      "categoryName": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|businessNumber|string|false|none|none|
|sellerIntro|string|false|none|none|
|sellerEmail|string|false|none|none|
|sellerPhone|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|sellerGrade|string|false|none|none|
|products|[[ProductResponse](#schemaproductresponse)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|

<h2 id="tocS_OrderRequestItem">OrderRequestItem</h2>
<!-- backwards compatibility -->
<a id="schemaorderrequestitem"></a>
<a id="schema_OrderRequestItem"></a>
<a id="tocSorderrequestitem"></a>
<a id="tocsorderrequestitem"></a>

```json
{
  "productId": "string",
  "quantity": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string|false|none|none|
|quantity|integer(int32)|false|none|none|

<h2 id="tocS_OrderSheetRequest">OrderSheetRequest</h2>
<!-- backwards compatibility -->
<a id="schemaordersheetrequest"></a>
<a id="schema_OrderSheetRequest"></a>
<a id="tocSordersheetrequest"></a>
<a id="tocsordersheetrequest"></a>

```json
{
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cartItemIds|[string]|false|none|none|
|directOrderItem|[OrderRequestItem](#schemaorderrequestitem)|false|none|none|
|fromCart|boolean|false|none|none|

<h2 id="tocS_CartItemDto">CartItemDto</h2>
<!-- backwards compatibility -->
<a id="schemacartitemdto"></a>
<a id="schema_CartItemDto"></a>
<a id="tocScartitemdto"></a>
<a id="tocscartitemdto"></a>

```json
{
  "cartItemId": "40ef0f19-abce-482c-a3e0-a00600ffe072",
  "cartId": "a978ee3d-b7bf-468a-b84b-28f1d6366abc",
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "productName": "string",
  "productPrice": 0,
  "categoryName": "string",
  "quantity": 0,
  "productImageUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cartItemId|string(uuid)|false|none|none|
|cartId|string(uuid)|false|none|none|
|productId|string(uuid)|false|none|none|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|categoryName|string|false|none|none|
|quantity|integer(int32)|false|none|none|
|productImageUrl|string|false|none|none|

<h2 id="tocS_OrderSheetResponse">OrderSheetResponse</h2>
<!-- backwards compatibility -->
<a id="schemaordersheetresponse"></a>
<a id="schema_OrderSheetResponse"></a>
<a id="tocSordersheetresponse"></a>
<a id="tocsordersheetresponse"></a>

```json
{
  "items": [
    {
      "cartItemId": "40ef0f19-abce-482c-a3e0-a00600ffe072",
      "cartId": "a978ee3d-b7bf-468a-b84b-28f1d6366abc",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
      "sellerName": "string",
      "productName": "string",
      "productPrice": 0,
      "categoryName": "string",
      "quantity": 0,
      "productImageUrl": "string"
    }
  ],
  "totalAmount": 0,
  "shippingFee": 0,
  "finalAmount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[CartItemDto](#schemacartitemdto)]|false|none|none|
|totalAmount|integer(int32)|false|none|none|
|shippingFee|integer(int32)|false|none|none|
|finalAmount|integer(int32)|false|none|none|

<h2 id="tocS_OrderConfirmRequest">OrderConfirmRequest</h2>
<!-- backwards compatibility -->
<a id="schemaorderconfirmrequest"></a>
<a id="schema_OrderConfirmRequest"></a>
<a id="tocSorderconfirmrequest"></a>
<a id="tocsorderconfirmrequest"></a>

```json
{
  "orderItemId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderItemId|string|true|none|none|

<h2 id="tocS_OrderCancelRequest">OrderCancelRequest</h2>
<!-- backwards compatibility -->
<a id="schemaordercancelrequest"></a>
<a id="schema_OrderCancelRequest"></a>
<a id="tocSordercancelrequest"></a>
<a id="tocsordercancelrequest"></a>

```json
{
  "orderItemId": "string",
  "reason": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderItemId|string|true|none|none|
|reason|string|true|none|none|

<h2 id="tocS_UserA11yProfileResponse">UserA11yProfileResponse</h2>
<!-- backwards compatibility -->
<a id="schemausera11yprofileresponse"></a>
<a id="schema_UserA11yProfileResponse"></a>
<a id="tocSusera11yprofileresponse"></a>
<a id="tocsusera11yprofileresponse"></a>

```json
{
  "profileId": "faebe71b-2bf8-4bdb-9b67-258e4d6aa00a",
  "profileName": "string",
  "description": "string",
  "contrastLevel": 0,
  "textSizeLevel": 0,
  "textSpacingLevel": 0,
  "lineHeightLevel": 0,
  "textAlign": "string",
  "screenReader": true,
  "smartContrast": true,
  "highlightLinks": true,
  "cursorHighlight": true,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|profileId|string(uuid)|false|none|none|
|profileName|string|false|none|none|
|description|string|false|none|none|
|contrastLevel|integer(int32)|false|none|none|
|textSizeLevel|integer(int32)|false|none|none|
|textSpacingLevel|integer(int32)|false|none|none|
|lineHeightLevel|integer(int32)|false|none|none|
|textAlign|string|false|none|none|
|screenReader|boolean|false|none|none|
|smartContrast|boolean|false|none|none|
|highlightLinks|boolean|false|none|none|
|cursorHighlight|boolean|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|

<h2 id="tocS_SellerProductRegisterRequest">SellerProductRegisterRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerproductregisterrequest"></a>
<a id="schema_SellerProductRegisterRequest"></a>
<a id="tocSsellerproductregisterrequest"></a>
<a id="tocssellerproductregisterrequest"></a>

```json
{
  "productName": "string",
  "productDescription": "string",
  "categoryId": "string",
  "productPrice": 0,
  "productStock": 0,
  "imageMetadataList": [
    {
      "originalFileName": "string",
      "altText": "string",
      "sequence": 0,
      "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
      "isNew": true
    }
  ]
}

```

Product registration data

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productName|string|true|none|none|
|productDescription|string|true|none|none|
|categoryId|string|true|none|none|
|productPrice|integer(int32)|true|none|none|
|productStock|integer(int32)|true|none|none|
|imageMetadataList|[[ImageMetadata](#schemaimagemetadata)]|false|none|none|

<h2 id="tocS_ProductDetailResponse">ProductDetailResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductdetailresponse"></a>
<a id="schema_ProductDetailResponse"></a>
<a id="tocSproductdetailresponse"></a>
<a id="tocsproductdetailresponse"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "sellerGrade": "NEWER",
  "isA11yGuarantee": true,
  "productPrice": 0,
  "productStatus": "PENDING",
  "productDescription": "string",
  "productStock": 0,
  "productImages": [
    {
      "imageId": "bbefe473-c66a-4040-85cf-1c7e6f0b3830",
      "imageUrl": "string",
      "altText": "string",
      "imageSequence": 0
    }
  ],
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string",
  "summaryText": "string",
  "usageContext": "string",
  "submitDate": "2019-08-24T14:15:22Z",
  "usageMethod": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|sellerGrade|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productStatus|string|false|none|none|
|productDescription|string|false|none|none|
|productStock|integer(int32)|false|none|none|
|productImages|[[ProductImageResponse](#schemaproductimageresponse)]|false|none|none|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|
|summaryText|string|false|none|none|
|usageContext|string|false|none|none|
|submitDate|string(date-time)|false|none|none|
|usageMethod|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

<h2 id="tocS_SellerOrderClaimProcessRequest">SellerOrderClaimProcessRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerorderclaimprocessrequest"></a>
<a id="schema_SellerOrderClaimProcessRequest"></a>
<a id="tocSsellerorderclaimprocessrequest"></a>
<a id="tocssellerorderclaimprocessrequest"></a>

```json
{
  "action": "APPROVED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|action|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|action|APPROVED|
|action|REJECTED|

<h2 id="tocS_SellerApplyRequest">SellerApplyRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerapplyrequest"></a>
<a id="schema_SellerApplyRequest"></a>
<a id="tocSsellerapplyrequest"></a>
<a id="tocssellerapplyrequest"></a>

```json
{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerIntro": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerName|string|true|none|none|
|businessNumber|string|true|none|none|
|sellerIntro|string|false|none|none|

<h2 id="tocS_SellerApplyResponse">SellerApplyResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerapplyresponse"></a>
<a id="schema_SellerApplyResponse"></a>
<a id="tocSsellerapplyresponse"></a>
<a id="tocssellerapplyresponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "sellerIntro": "string",
  "a11yGuarantee": true,
  "sellerSubmitStatus": "PENDING",
  "submitDate": "2019-08-24T14:15:22Z",
  "approvedDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userPhone|string|false|none|none|
|businessNumber|string|false|none|none|
|sellerGrade|string|false|none|none|
|sellerIntro|string|false|none|none|
|a11yGuarantee|boolean|false|none|none|
|sellerSubmitStatus|string|false|none|none|
|submitDate|string(date-time)|false|none|none|
|approvedDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|sellerSubmitStatus|PENDING|
|sellerSubmitStatus|APPROVED|
|sellerSubmitStatus|REJECTED|

<h2 id="tocS_PaymentVerifyRequest">PaymentVerifyRequest</h2>
<!-- backwards compatibility -->
<a id="schemapaymentverifyrequest"></a>
<a id="schema_PaymentVerifyRequest"></a>
<a id="tocSpaymentverifyrequest"></a>
<a id="tocspaymentverifyrequest"></a>

```json
{
  "orderId": "string",
  "amount": 0,
  "method": "string",
  "paymentKey": "string",
  "impUid": "string",
  "cartItemIdsToDelete": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string|false|none|none|
|amount|integer(int32)|false|none|none|
|method|string|true|none|none|
|paymentKey|string|false|none|none|
|impUid|string|false|none|none|
|cartItemIdsToDelete|[string]|false|none|none|

<h2 id="tocS_PaymentVerifyResponse">PaymentVerifyResponse</h2>
<!-- backwards compatibility -->
<a id="schemapaymentverifyresponse"></a>
<a id="schema_PaymentVerifyResponse"></a>
<a id="tocSpaymentverifyresponse"></a>
<a id="tocspaymentverifyresponse"></a>

```json
{
  "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
  "status": "string",
  "amount": 0,
  "paidAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string(uuid)|false|none|none|
|status|string|false|none|none|
|amount|integer(int32)|false|none|none|
|paidAt|string(date-time)|false|none|none|

<h2 id="tocS_OrderCreateRequest">OrderCreateRequest</h2>
<!-- backwards compatibility -->
<a id="schemaordercreaterequest"></a>
<a id="schema_OrderCreateRequest"></a>
<a id="tocSordercreaterequest"></a>
<a id="tocsordercreaterequest"></a>

```json
{
  "addressId": "string",
  "cartItemIds": [
    "string"
  ],
  "directOrderItem": {
    "productId": "string",
    "quantity": 0
  },
  "fromCart": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|addressId|string|false|none|none|
|cartItemIds|[string]|false|none|none|
|directOrderItem|[OrderRequestItem](#schemaorderrequestitem)|false|none|none|
|fromCart|boolean|false|none|none|

<h2 id="tocS_OrderItemResponse">OrderItemResponse</h2>
<!-- backwards compatibility -->
<a id="schemaorderitemresponse"></a>
<a id="schema_OrderItemResponse"></a>
<a id="tocSorderitemresponse"></a>
<a id="tocsorderitemresponse"></a>

```json
{
  "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "categoryName": "string",
  "productPrice": 0,
  "productQuantity": 0,
  "productTotalPrice": 0,
  "productImageUrl": "string",
  "orderItemStatus": "ORDERED",
  "cancelReason": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderItemId|string(uuid)|false|none|none|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|categoryName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productQuantity|integer(int32)|false|none|none|
|productTotalPrice|integer(int32)|false|none|none|
|productImageUrl|string|false|none|none|
|orderItemStatus|string|false|none|none|
|cancelReason|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

<h2 id="tocS_OrderResponse">OrderResponse</h2>
<!-- backwards compatibility -->
<a id="schemaorderresponse"></a>
<a id="schema_OrderResponse"></a>
<a id="tocSorderresponse"></a>
<a id="tocsorderresponse"></a>

```json
{
  "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
  "totalPrice": 0,
  "orderItems": [
    {
      "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "categoryName": "string",
      "productPrice": 0,
      "productQuantity": 0,
      "productTotalPrice": 0,
      "productImageUrl": "string",
      "orderItemStatus": "ORDERED",
      "cancelReason": "string"
    }
  ],
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string(uuid)|false|none|none|
|totalPrice|integer(int32)|false|none|none|
|orderItems|[[OrderItemResponse](#schemaorderitemresponse)]|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_CartAddRequest">CartAddRequest</h2>
<!-- backwards compatibility -->
<a id="schemacartaddrequest"></a>
<a id="schema_CartAddRequest"></a>
<a id="tocScartaddrequest"></a>
<a id="tocscartaddrequest"></a>

```json
{
  "productId": "string",
  "quantity": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string|true|none|none|
|quantity|integer(int32)|true|none|none|

<h2 id="tocS_CartItemUpdatedResponse">CartItemUpdatedResponse</h2>
<!-- backwards compatibility -->
<a id="schemacartitemupdatedresponse"></a>
<a id="schema_CartItemUpdatedResponse"></a>
<a id="tocScartitemupdatedresponse"></a>
<a id="tocscartitemupdatedresponse"></a>

```json
{
  "cartItemId": "40ef0f19-abce-482c-a3e0-a00600ffe072",
  "cartId": "a978ee3d-b7bf-468a-b84b-28f1d6366abc",
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "quantity": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cartItemId|string(uuid)|false|none|none|
|cartId|string(uuid)|false|none|none|
|productId|string(uuid)|false|none|none|
|quantity|integer(int32)|false|none|none|

<h2 id="tocS_RefreshRequest">RefreshRequest</h2>
<!-- backwards compatibility -->
<a id="schemarefreshrequest"></a>
<a id="schema_RefreshRequest"></a>
<a id="tocSrefreshrequest"></a>
<a id="tocsrefreshrequest"></a>

```json
{
  "refreshToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|refreshToken|string|true|none|none|

<h2 id="tocS_JwtResponse">JwtResponse</h2>
<!-- backwards compatibility -->
<a id="schemajwtresponse"></a>
<a id="schema_JwtResponse"></a>
<a id="tocSjwtresponse"></a>
<a id="tocsjwtresponse"></a>

```json
{
  "accessToken": "string",
  "refreshToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accessToken|string|false|none|none|
|refreshToken|string|false|none|none|

<h2 id="tocS_LoginRequest">LoginRequest</h2>
<!-- backwards compatibility -->
<a id="schemaloginrequest"></a>
<a id="schema_LoginRequest"></a>
<a id="tocSloginrequest"></a>
<a id="tocsloginrequest"></a>

```json
{
  "email": "string",
  "password": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|false|none|none|
|password|string|false|none|none|

<h2 id="tocS_LoginResponse">LoginResponse</h2>
<!-- backwards compatibility -->
<a id="schemaloginresponse"></a>
<a id="schema_LoginResponse"></a>
<a id="tocSloginresponse"></a>
<a id="tocsloginresponse"></a>

```json
{
  "user": {
    "userEmail": "string",
    "userNickname": "string",
    "userRole": "USER"
  },
  "accessToken": "string",
  "refreshToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|[UserInfo](#schemauserinfo)|false|none|none|
|accessToken|string|false|none|none|
|refreshToken|string|false|none|none|

<h2 id="tocS_UserInfo">UserInfo</h2>
<!-- backwards compatibility -->
<a id="schemauserinfo"></a>
<a id="schema_UserInfo"></a>
<a id="tocSuserinfo"></a>
<a id="tocsuserinfo"></a>

```json
{
  "userEmail": "string",
  "userNickname": "string",
  "userRole": "USER"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userEmail|string|false|none|none|
|userNickname|string|false|none|none|
|userRole|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userRole|USER|
|userRole|SELLER|
|userRole|ADMIN|
|userRole|TEMP|

<h2 id="tocS_KakaoSignUpRequest">KakaoSignUpRequest</h2>
<!-- backwards compatibility -->
<a id="schemakakaosignuprequest"></a>
<a id="schema_KakaoSignUpRequest"></a>
<a id="tocSkakaosignuprequest"></a>
<a id="tocskakaosignuprequest"></a>

```json
{
  "userEmail": "string",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userEmail|string|true|none|none|
|userName|string|true|none|none|
|userNickname|string|false|none|none|
|userPhone|string|true|none|none|

<h2 id="tocS_UserResponse">UserResponse</h2>
<!-- backwards compatibility -->
<a id="schemauserresponse"></a>
<a id="schema_UserResponse"></a>
<a id="tocSuserresponse"></a>
<a id="tocsuserresponse"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "userNickname": "string",
  "userRole": "USER",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "sellerSubmitStatus": "PENDING"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userPhone|string|false|none|none|
|userNickname|string|false|none|none|
|userRole|string|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|sellerSubmitStatus|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userRole|USER|
|userRole|SELLER|
|userRole|ADMIN|
|userRole|TEMP|
|sellerSubmitStatus|PENDING|
|sellerSubmitStatus|APPROVED|
|sellerSubmitStatus|REJECTED|

<h2 id="tocS_JoinRequest">JoinRequest</h2>
<!-- backwards compatibility -->
<a id="schemajoinrequest"></a>
<a id="schema_JoinRequest"></a>
<a id="tocSjoinrequest"></a>
<a id="tocsjoinrequest"></a>

```json
{
  "userEmail": "string",
  "userPass": "stringst",
  "userName": "string",
  "userNickname": "string",
  "userPhone": "stringstri"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userEmail|string|true|none|none|
|userPass|string|true|none|none|
|userName|string|true|none|none|
|userNickname|string|false|none|none|
|userPhone|string|false|none|none|

<h2 id="tocS_UserUpdateRequest">UserUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemauserupdaterequest"></a>
<a id="schema_UserUpdateRequest"></a>
<a id="tocSuserupdaterequest"></a>
<a id="tocsuserupdaterequest"></a>

```json
{
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "userNickname": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userPhone|string|false|none|none|
|userNickname|string|false|none|none|

<h2 id="tocS_DefaultAddressRequest">DefaultAddressRequest</h2>
<!-- backwards compatibility -->
<a id="schemadefaultaddressrequest"></a>
<a id="schema_DefaultAddressRequest"></a>
<a id="tocSdefaultaddressrequest"></a>
<a id="tocsdefaultaddressrequest"></a>

```json
{
  "addressId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|addressId|string|true|none|none|

<h2 id="tocS_SellerProductStockUpdateRequest">SellerProductStockUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerproductstockupdaterequest"></a>
<a id="schema_SellerProductStockUpdateRequest"></a>
<a id="tocSsellerproductstockupdaterequest"></a>
<a id="tocssellerproductstockupdaterequest"></a>

```json
{
  "productStock": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productStock|integer(int32)|true|none|none|

<h2 id="tocS_SellerOrderItemsStatusUpdateRequest">SellerOrderItemsStatusUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerorderitemsstatusupdaterequest"></a>
<a id="schema_SellerOrderItemsStatusUpdateRequest"></a>
<a id="tocSsellerorderitemsstatusupdaterequest"></a>
<a id="tocssellerorderitemsstatusupdaterequest"></a>

```json
{
  "status": "ORDERED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|ORDERED|
|status|PAID|
|status|REJECTED|
|status|ACCEPTED|
|status|SHIPPING|
|status|SHIPPED|
|status|CONFIRMED|
|status|CANCEL_PENDING|
|status|CANCELED|
|status|CANCEL_REJECTED|
|status|RETURN_PENDING|
|status|RETURNED|
|status|RETURN_REJECTED|

<h2 id="tocS_CartQtyUpdateRequest">CartQtyUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemacartqtyupdaterequest"></a>
<a id="schema_CartQtyUpdateRequest"></a>
<a id="tocScartqtyupdaterequest"></a>
<a id="tocscartqtyupdaterequest"></a>

```json
{
  "quantity": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|quantity|integer(int32)|true|none|none|

<h2 id="tocS_AdminSellerUpdateRequest">AdminSellerUpdateRequest</h2>
<!-- backwards compatibility -->
<a id="schemaadminsellerupdaterequest"></a>
<a id="schema_AdminSellerUpdateRequest"></a>
<a id="tocSadminsellerupdaterequest"></a>
<a id="tocsadminsellerupdaterequest"></a>

```json
{
  "sellerName": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "sellerIntro": "string",
  "a11yGuarantee": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerName|string|false|none|none|
|businessNumber|string|false|none|none|
|sellerGrade|string|false|none|none|
|sellerIntro|string|false|none|none|
|a11yGuarantee|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|

<h2 id="tocS_OrderDetailResponse">OrderDetailResponse</h2>
<!-- backwards compatibility -->
<a id="schemaorderdetailresponse"></a>
<a id="schema_OrderDetailResponse"></a>
<a id="tocSorderdetailresponse"></a>
<a id="tocsorderdetailresponse"></a>

```json
{
  "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "totalPrice": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "orderItem": {
    "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
    "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
    "productName": "string",
    "categoryName": "string",
    "productPrice": 0,
    "productQuantity": 0,
    "productTotalPrice": 0,
    "productImageUrl": "string",
    "orderItemStatus": "ORDERED",
    "cancelReason": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string(uuid)|false|none|none|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userPhone|string|false|none|none|
|receiverName|string|false|none|none|
|receiverPhone|string|false|none|none|
|receiverZipcode|string|false|none|none|
|receiverAddr1|string|false|none|none|
|receiverAddr2|string|false|none|none|
|totalPrice|integer(int32)|false|none|none|
|createdAt|string(date-time)|false|none|none|
|orderItem|[OrderItemResponse](#schemaorderitemresponse)|false|none|none|

<h2 id="tocS_SellerInquireProductRequest">SellerInquireProductRequest</h2>
<!-- backwards compatibility -->
<a id="schemasellerinquireproductrequest"></a>
<a id="schema_SellerInquireProductRequest"></a>
<a id="tocSsellerinquireproductrequest"></a>
<a id="tocssellerinquireproductrequest"></a>

```json
{
  "page": 0,
  "size": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|

<h2 id="tocS_ProductInquireResponse">ProductInquireResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductinquireresponse"></a>
<a id="schema_ProductInquireResponse"></a>
<a id="tocSproductinquireresponse"></a>
<a id="tocsproductinquireresponse"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productStock": 0,
  "productStatus": "PENDING",
  "categoryName": "string",
  "approvedAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productStock|integer(int32)|false|none|none|
|productStatus|string|false|none|none|
|categoryName|string|false|none|none|
|approvedAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

<h2 id="tocS_SellerOrderSummaryResponse">SellerOrderSummaryResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerordersummaryresponse"></a>
<a id="schema_SellerOrderSummaryResponse"></a>
<a id="tocSsellerordersummaryresponse"></a>
<a id="tocssellerordersummaryresponse"></a>

```json
{
  "newOrders": 0,
  "acceptedOrders": 0,
  "shippingOrders": 0,
  "completedOrders": 0,
  "claimedOrders": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|newOrders|integer(int64)|false|none|none|
|acceptedOrders|integer(int64)|false|none|none|
|shippingOrders|integer(int64)|false|none|none|
|completedOrders|integer(int64)|false|none|none|
|claimedOrders|integer(int64)|false|none|none|

<h2 id="tocS_SellerOrderInquireResponse">SellerOrderInquireResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerorderinquireresponse"></a>
<a id="schema_SellerOrderInquireResponse"></a>
<a id="tocSsellerorderinquireresponse"></a>
<a id="tocssellerorderinquireresponse"></a>

```json
{
  "orderItems": [
    {
      "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
      "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "productPrice": 0,
      "productQuantity": 0,
      "orderItemStatus": "ORDERED",
      "buyerName": "string",
      "buyerEmail": "string",
      "buyerPhone": "string",
      "orderedAt": "2019-08-24T14:15:22Z"
    }
  ],
  "totalOrderCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderItems|[[SellerOrderItemResponse](#schemasellerorderitemresponse)]|false|none|none|
|totalOrderCount|integer(int32)|false|none|none|

<h2 id="tocS_SellerOrderItemResponse">SellerOrderItemResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerorderitemresponse"></a>
<a id="schema_SellerOrderItemResponse"></a>
<a id="tocSsellerorderitemresponse"></a>
<a id="tocssellerorderitemresponse"></a>

```json
{
  "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
  "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productQuantity": 0,
  "orderItemStatus": "ORDERED",
  "buyerName": "string",
  "buyerEmail": "string",
  "buyerPhone": "string",
  "orderedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderItemId|string(uuid)|false|none|none|
|orderId|string(uuid)|false|none|none|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productQuantity|integer(int32)|false|none|none|
|orderItemStatus|string|false|none|none|
|buyerName|string|false|none|none|
|buyerEmail|string|false|none|none|
|buyerPhone|string|false|none|none|
|orderedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|orderItemStatus|ORDERED|
|orderItemStatus|PAID|
|orderItemStatus|REJECTED|
|orderItemStatus|ACCEPTED|
|orderItemStatus|SHIPPING|
|orderItemStatus|SHIPPED|
|orderItemStatus|CONFIRMED|
|orderItemStatus|CANCEL_PENDING|
|orderItemStatus|CANCELED|
|orderItemStatus|CANCEL_REJECTED|
|orderItemStatus|RETURN_PENDING|
|orderItemStatus|RETURNED|
|orderItemStatus|RETURN_REJECTED|

<h2 id="tocS_SellerTopProductResponse">SellerTopProductResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellertopproductresponse"></a>
<a id="schema_SellerTopProductResponse"></a>
<a id="tocSsellertopproductresponse"></a>
<a id="tocssellertopproductresponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productImageUrl": "string",
  "orderCount": 0,
  "totalQuantitySold": 0,
  "totalSalesAmount": 0,
  "salesRank": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productImageUrl|string|false|none|none|
|orderCount|integer(int64)|false|none|none|
|totalQuantitySold|integer(int64)|false|none|none|
|totalSalesAmount|number|false|none|none|
|salesRank|integer(int32)|false|none|none|

<h2 id="tocS_SellerDashboardResponse">SellerDashboardResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerdashboardresponse"></a>
<a id="schema_SellerDashboardResponse"></a>
<a id="tocSsellerdashboardresponse"></a>
<a id="tocssellerdashboardresponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "sellerIntro": "string",
  "totalRevenue": 0,
  "totalOrderCount": 0,
  "refundRate": 0,
  "confirmedRate": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|sellerIntro|string|false|none|none|
|totalRevenue|number|false|none|none|
|totalOrderCount|integer(int64)|false|none|none|
|refundRate|number|false|none|none|
|confirmedRate|number|false|none|none|

<h2 id="tocS_DailyRevenueDto">DailyRevenueDto</h2>
<!-- backwards compatibility -->
<a id="schemadailyrevenuedto"></a>
<a id="schema_DailyRevenueDto"></a>
<a id="tocSdailyrevenuedto"></a>
<a id="tocsdailyrevenuedto"></a>

```json
{
  "orderDate": "2019-08-24T14:15:22Z",
  "dailyRevenue": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderDate|string(date-time)|false|none|none|
|dailyRevenue|number|false|none|none|

<h2 id="tocS_MonthlyPopularProduct">MonthlyPopularProduct</h2>
<!-- backwards compatibility -->
<a id="schemamonthlypopularproduct"></a>
<a id="schema_MonthlyPopularProduct"></a>
<a id="tocSmonthlypopularproduct"></a>
<a id="tocsmonthlypopularproduct"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productImageUrl": "string",
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string",
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "monthlySalesVolume": 0,
  "monthlyOrderCount": 0,
  "ranking": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|number|false|none|none|
|productImageUrl|string|false|none|none|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|
|sellerId|string(uuid)|false|none|none|
|monthlySalesVolume|integer(int64)|false|none|none|
|monthlyOrderCount|integer(int64)|false|none|none|
|ranking|integer(int32)|false|none|none|

<h2 id="tocS_CatProductInfo">CatProductInfo</h2>
<!-- backwards compatibility -->
<a id="schemacatproductinfo"></a>
<a id="schema_CatProductInfo"></a>
<a id="tocScatproductinfo"></a>
<a id="tocscatproductinfo"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "productPrice": 0,
  "productImageUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productImageUrl|string|false|none|none|

<h2 id="tocS_CategoryRecommendResponse">CategoryRecommendResponse</h2>
<!-- backwards compatibility -->
<a id="schemacategoryrecommendresponse"></a>
<a id="schema_CategoryRecommendResponse"></a>
<a id="tocScategoryrecommendresponse"></a>
<a id="tocscategoryrecommendresponse"></a>

```json
{
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string",
  "products": [
    {
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "productPrice": 0,
      "productImageUrl": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|
|products|[[CatProductInfo](#schemacatproductinfo)]|false|none|none|

<h2 id="tocS_EventResponse">EventResponse</h2>
<!-- backwards compatibility -->
<a id="schemaeventresponse"></a>
<a id="schema_EventResponse"></a>
<a id="tocSeventresponse"></a>
<a id="tocseventresponse"></a>

```json
{
  "eventTitle": "string",
  "eventDescription": "string",
  "eventImageUrl": "string",
  "eventUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|eventTitle|string|false|none|none|
|eventDescription|string|false|none|none|
|eventImageUrl|string|false|none|none|
|eventUrl|string|false|none|none|

<h2 id="tocS_CategoryResponse">CategoryResponse</h2>
<!-- backwards compatibility -->
<a id="schemacategoryresponse"></a>
<a id="schema_CategoryResponse"></a>
<a id="tocScategoryresponse"></a>
<a id="tocscategoryresponse"></a>

```json
{
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|

<h2 id="tocS_CartItemListDto">CartItemListDto</h2>
<!-- backwards compatibility -->
<a id="schemacartitemlistdto"></a>
<a id="schema_CartItemListDto"></a>
<a id="tocScartitemlistdto"></a>
<a id="tocscartitemlistdto"></a>

```json
{
  "sellerName": "string",
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "groupTotal": 0,
  "items": [
    {
      "cartItemId": "40ef0f19-abce-482c-a3e0-a00600ffe072",
      "cartId": "a978ee3d-b7bf-468a-b84b-28f1d6366abc",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
      "sellerName": "string",
      "productName": "string",
      "productPrice": 0,
      "categoryName": "string",
      "quantity": 0,
      "productImageUrl": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerName|string|false|none|none|
|sellerId|string(uuid)|false|none|none|
|groupTotal|integer(int32)|false|none|none|
|items|[[CartItemDto](#schemacartitemdto)]|false|none|none|

<h2 id="tocS_CartItemListResponse">CartItemListResponse</h2>
<!-- backwards compatibility -->
<a id="schemacartitemlistresponse"></a>
<a id="schema_CartItemListResponse"></a>
<a id="tocScartitemlistresponse"></a>
<a id="tocscartitemlistresponse"></a>

```json
{
  "items": [
    {
      "sellerName": "string",
      "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
      "groupTotal": 0,
      "items": [
        {
          "cartItemId": "40ef0f19-abce-482c-a3e0-a00600ffe072",
          "cartId": "a978ee3d-b7bf-468a-b84b-28f1d6366abc",
          "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
          "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
          "sellerName": "string",
          "productName": "string",
          "productPrice": 0,
          "categoryName": "string",
          "quantity": 0,
          "productImageUrl": "string"
        }
      ]
    }
  ],
  "total": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[CartItemListDto](#schemacartitemlistdto)]|false|none|none|
|total|integer(int32)|false|none|none|

<h2 id="tocS_CartItemCountResponse">CartItemCountResponse</h2>
<!-- backwards compatibility -->
<a id="schemacartitemcountresponse"></a>
<a id="schema_CartItemCountResponse"></a>
<a id="tocScartitemcountresponse"></a>
<a id="tocscartitemcountresponse"></a>

```json
{
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer(int32)|false|none|none|

<h2 id="tocS_CheckExistsResponse">CheckExistsResponse</h2>
<!-- backwards compatibility -->
<a id="schemacheckexistsresponse"></a>
<a id="schema_CheckExistsResponse"></a>
<a id="tocScheckexistsresponse"></a>
<a id="tocscheckexistsresponse"></a>

```json
{
  "isAvailable": "AVAILABLE"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isAvailable|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|isAvailable|AVAILABLE|
|isAvailable|UNAVAILABLE|

<h2 id="tocS_UserAdminResponse">UserAdminResponse</h2>
<!-- backwards compatibility -->
<a id="schemauseradminresponse"></a>
<a id="schema_UserAdminResponse"></a>
<a id="tocSuseradminresponse"></a>
<a id="tocsuseradminresponse"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "userName": "string",
  "userEmail": "string",
  "userNickname": "string",
  "userRole": "USER",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userNickname|string|false|none|none|
|userRole|string|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userRole|USER|
|userRole|SELLER|
|userRole|ADMIN|
|userRole|TEMP|

<h2 id="tocS_SellerProfileResponse">SellerProfileResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerprofileresponse"></a>
<a id="schema_SellerProfileResponse"></a>
<a id="tocSsellerprofileresponse"></a>
<a id="tocssellerprofileresponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "contactEmail": "string",
  "contactPhone": "string",
  "storeIntro": "string",
  "isA11yGuarantee": true,
  "profileStatus": "PENDING",
  "submitDate": "2019-08-24T14:15:22Z",
  "approvedDate": "2019-08-24T14:15:22Z",
  "lastUpdatedDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|businessNumber|string|false|none|none|
|sellerGrade|string|false|none|none|
|contactEmail|string|false|none|none|
|contactPhone|string|false|none|none|
|storeIntro|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|profileStatus|string|false|none|none|
|submitDate|string(date-time)|false|none|none|
|approvedDate|string(date-time)|false|none|none|
|lastUpdatedDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|profileStatus|PENDING|
|profileStatus|APPROVED|
|profileStatus|REJECTED|

<h2 id="tocS_SellerDetailResponse">SellerDetailResponse</h2>
<!-- backwards compatibility -->
<a id="schemasellerdetailresponse"></a>
<a id="schema_SellerDetailResponse"></a>
<a id="tocSsellerdetailresponse"></a>
<a id="tocssellerdetailresponse"></a>

```json
{
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "businessNumber": "string",
  "sellerGrade": "NEWER",
  "contactEmail": "string",
  "contactPhone": "string",
  "storeIntro": "string",
  "isA11yGuarantee": true,
  "profileStatus": "PENDING",
  "submitDate": "2019-08-24T14:15:22Z",
  "approvedDate": "2019-08-24T14:15:22Z",
  "lastUpdatedDate": "2019-08-24T14:15:22Z",
  "orders": [
    {
      "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "categoryName": "string",
      "productPrice": 0,
      "productQuantity": 0,
      "productTotalPrice": 0,
      "productImageUrl": "string",
      "orderItemStatus": "ORDERED",
      "cancelReason": "string"
    }
  ],
  "products": [
    {
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "productPrice": 0,
      "productStock": 0,
      "productStatus": "PENDING",
      "categoryName": "string",
      "approvedAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|businessNumber|string|false|none|none|
|sellerGrade|string|false|none|none|
|contactEmail|string|false|none|none|
|contactPhone|string|false|none|none|
|storeIntro|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|profileStatus|string|false|none|none|
|submitDate|string(date-time)|false|none|none|
|approvedDate|string(date-time)|false|none|none|
|lastUpdatedDate|string(date-time)|false|none|none|
|orders|[[OrderItemResponse](#schemaorderitemresponse)]|false|none|none|
|products|[[ProductInquireResponse](#schemaproductinquireresponse)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|profileStatus|PENDING|
|profileStatus|APPROVED|
|profileStatus|REJECTED|

<h2 id="tocS_AdminProductsResponse">AdminProductsResponse</h2>
<!-- backwards compatibility -->
<a id="schemaadminproductsresponse"></a>
<a id="schema_AdminProductsResponse"></a>
<a id="tocSadminproductsresponse"></a>
<a id="tocsadminproductsresponse"></a>

```json
{
  "totalCount": 0,
  "products": [
    {
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
      "sellerName": "string",
      "sellerGrade": "NEWER",
      "isA11yGuarantee": true,
      "productPrice": 0,
      "productStatus": "PENDING",
      "productDescription": "string",
      "productStock": 0,
      "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
      "categoryName": "string",
      "submitDate": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalCount|integer(int32)|false|none|none|
|products|[[ProductAdminInquireResponse](#schemaproductadmininquireresponse)]|false|none|none|

<h2 id="tocS_ProductAdminInquireResponse">ProductAdminInquireResponse</h2>
<!-- backwards compatibility -->
<a id="schemaproductadmininquireresponse"></a>
<a id="schema_ProductAdminInquireResponse"></a>
<a id="tocSproductadmininquireresponse"></a>
<a id="tocsproductadmininquireresponse"></a>

```json
{
  "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
  "productName": "string",
  "sellerId": "2b5cb5ab-0f11-4d75-8f0a-a6d87a9d534e",
  "sellerName": "string",
  "sellerGrade": "NEWER",
  "isA11yGuarantee": true,
  "productPrice": 0,
  "productStatus": "PENDING",
  "productDescription": "string",
  "productStock": 0,
  "categoryId": "337f5e5d-288b-40d5-be14-901cc3acacc0",
  "categoryName": "string",
  "submitDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(uuid)|false|none|none|
|productName|string|false|none|none|
|sellerId|string(uuid)|false|none|none|
|sellerName|string|false|none|none|
|sellerGrade|string|false|none|none|
|isA11yGuarantee|boolean|false|none|none|
|productPrice|integer(int32)|false|none|none|
|productStatus|string|false|none|none|
|productDescription|string|false|none|none|
|productStock|integer(int32)|false|none|none|
|categoryId|string(uuid)|false|none|none|
|categoryName|string|false|none|none|
|submitDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|sellerGrade|NEWER|
|sellerGrade|REGULAR|
|sellerGrade|TRUSTED|
|productStatus|PENDING|
|productStatus|APPROVED|
|productStatus|REJECTED|
|productStatus|PAUSED|
|productStatus|DELETED|

<h2 id="tocS_AdminOrderSearchRequest">AdminOrderSearchRequest</h2>
<!-- backwards compatibility -->
<a id="schemaadminordersearchrequest"></a>
<a id="schema_AdminOrderSearchRequest"></a>
<a id="tocSadminordersearchrequest"></a>
<a id="tocsadminordersearchrequest"></a>

```json
{
  "searchType": "string",
  "keyword": "string",
  "status": "PENDING",
  "startDate": "string",
  "endDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|searchType|string|false|none|none|
|keyword|string|false|none|none|
|status|string|false|none|none|
|startDate|string|false|none|none|
|endDate|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PENDING|
|status|PAID|
|status|DEPRECATED|

<h2 id="tocS_AdminOrderResponse">AdminOrderResponse</h2>
<!-- backwards compatibility -->
<a id="schemaadminorderresponse"></a>
<a id="schema_AdminOrderResponse"></a>
<a id="tocSadminorderresponse"></a>
<a id="tocsadminorderresponse"></a>

```json
{
  "orderId": "b3e1eced-f2bd-4d8c-9765-fbc9d1d222d5",
  "userName": "string",
  "userEmail": "string",
  "userPhone": "string",
  "receiverName": "string",
  "receiverPhone": "string",
  "receiverZipcode": "string",
  "receiverAddr1": "string",
  "receiverAddr2": "string",
  "totalPrice": 0,
  "items": [
    {
      "orderItemId": "33207bce-c741-4896-a76b-8afcf6e4179a",
      "productId": "dcd53ddb-8104-4e48-8cc0-5df1088c6113",
      "productName": "string",
      "categoryName": "string",
      "productPrice": 0,
      "productQuantity": 0,
      "productTotalPrice": 0,
      "productImageUrl": "string",
      "orderItemStatus": "ORDERED",
      "cancelReason": "string"
    }
  ],
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string(uuid)|false|none|none|
|userName|string|false|none|none|
|userEmail|string|false|none|none|
|userPhone|string|false|none|none|
|receiverName|string|false|none|none|
|receiverPhone|string|false|none|none|
|receiverZipcode|string|false|none|none|
|receiverAddr1|string|false|none|none|
|receiverAddr2|string|false|none|none|
|totalPrice|integer(int32)|false|none|none|
|items|[[OrderItemResponse](#schemaorderitemresponse)]|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_AdminDashboardStats">AdminDashboardStats</h2>
<!-- backwards compatibility -->
<a id="schemaadmindashboardstats"></a>
<a id="schema_AdminDashboardStats"></a>
<a id="tocSadmindashboardstats"></a>
<a id="tocsadmindashboardstats"></a>

```json
{
  "pendingSellerCount": 0,
  "pendingProductCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pendingSellerCount|integer(int32)|false|none|none|
|pendingProductCount|integer(int32)|false|none|none|

<h2 id="tocS_UserDeleteRequest">UserDeleteRequest</h2>
<!-- backwards compatibility -->
<a id="schemauserdeleterequest"></a>
<a id="schema_UserDeleteRequest"></a>
<a id="tocSuserdeleterequest"></a>
<a id="tocsuserdeleterequest"></a>

```json
{
  "userPassword": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userPassword|string|false|none|none|

<h2 id="tocS_CartItemDeleteRequest">CartItemDeleteRequest</h2>
<!-- backwards compatibility -->
<a id="schemacartitemdeleterequest"></a>
<a id="schema_CartItemDeleteRequest"></a>
<a id="tocScartitemdeleterequest"></a>
<a id="tocscartitemdeleterequest"></a>

```json
{
  "itemIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|itemIds|[string]|true|none|none|

