---
title: Api v0.1.0
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
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="api">Api v0.1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Library Nexus - Library Management System API

Base URLs:

* <a href="/api">/api</a>

<h1 id="api-health">health</h1>

Health operations

## healthCheck

<a id="opIdhealthCheck"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/healthz \
  -H 'Accept: application/json'

```

```http
GET /api/healthz HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/healthz',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/healthz',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/healthz', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/healthz', array(
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
URL obj = new URL("/api/healthz");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/healthz", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /healthz`

*Health check*

> Example responses

> 200 Response

```json
{
  "status": "string"
}
```

<h3 id="healthcheck-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Healthy|[HealthStatus](#schemahealthstatus)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-auth">auth</h1>

Authentication operations

## getMe

<a id="opIdgetMe"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/auth/me \
  -H 'Accept: application/json'

```

```http
GET /api/auth/me HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/auth/me',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/auth/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/auth/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/auth/me', array(
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
URL obj = new URL("/api/auth/me");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/auth/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /auth/me`

*Get current user info*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "clerkId": "string",
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "status": "string",
  "phone": "string",
  "createdAt": "string"
}
```

<h3 id="getme-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Current user|[UserProfile](#schemauserprofile)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-categories">categories</h1>

Book category operations

## listCategories

<a id="opIdlistCategories"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/categories \
  -H 'Accept: application/json'

```

```http
GET /api/categories HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/categories',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/categories', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/categories', array(
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
URL obj = new URL("/api/categories");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/categories", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /categories`

*List all categories*

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "categoryName": "string",
    "description": "string",
    "createdAt": "string",
    "updatedAt": "string"
  }
]
```

<h3 id="listcategories-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of categories|Inline|

<h3 id="listcategories-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Category](#schemacategory)]|false|none|none|
|» id|integer|true|none|none|
|» categoryName|string|true|none|none|
|» description|string,null|false|none|none|
|» createdAt|string|false|none|none|
|» updatedAt|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## createCategory

<a id="opIdcreateCategory"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/categories \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/categories HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "categoryName": "string",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/categories',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/categories', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/categories', array(
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
URL obj = new URL("/api/categories");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/categories", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /categories`

*Create a category*

> Body parameter

```json
{
  "categoryName": "string",
  "description": "string"
}
```

<h3 id="createcategory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CategoryInput](#schemacategoryinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "categoryName": "string",
  "description": "string",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createcategory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Category](#schemacategory)|

<aside class="success">
This operation does not require authentication
</aside>

## getCategory

<a id="opIdgetCategory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/categories/{id} \
  -H 'Accept: application/json'

```

```http
GET /api/categories/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/categories/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/categories/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/categories/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/categories/{id}', array(
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
URL obj = new URL("/api/categories/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/categories/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /categories/{id}`

*Get category by ID*

<h3 id="getcategory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "categoryName": "string",
  "description": "string",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="getcategory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Category|[Category](#schemacategory)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateCategory

<a id="opIdupdateCategory"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/categories/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/categories/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "categoryName": "string",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/categories/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/categories/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/categories/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/categories/{id}', array(
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
URL obj = new URL("/api/categories/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/categories/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /categories/{id}`

*Update a category*

> Body parameter

```json
{
  "categoryName": "string",
  "description": "string"
}
```

<h3 id="updatecategory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[CategoryUpdate](#schemacategoryupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "categoryName": "string",
  "description": "string",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updatecategory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[Category](#schemacategory)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteCategory

<a id="opIddeleteCategory"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/categories/{id}

```

```http
DELETE /api/categories/{id} HTTP/1.1

```

```javascript

fetch('/api/categories/{id}',
{
  method: 'DELETE'

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

result = RestClient.delete '/api/categories/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/api/categories/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/categories/{id}', array(
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
URL obj = new URL("/api/categories/{id}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/categories/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /categories/{id}`

*Delete a category*

<h3 id="deletecategory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

<h3 id="deletecategory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-books">books</h1>

Book operations

## listBooks

<a id="opIdlistBooks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/books \
  -H 'Accept: application/json'

```

```http
GET /api/books HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/books',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/books',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/books', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/books', array(
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
URL obj = new URL("/api/books");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/books", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /books`

*List books with optional filters*

<h3 id="listbooks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|
|categoryId|query|integer|false|none|
|availability|query|string|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|availability|available|
|availability|borrowed|
|availability|all|

> Example responses

> 200 Response

```json
{
  "books": [
    {
      "id": 0,
      "title": "string",
      "author": "string",
      "isbn": "string",
      "publisher": "string",
      "publicationYear": 0,
      "categoryId": 0,
      "categoryName": "string",
      "shelfLocation": "string",
      "description": "string",
      "coverImage": "string",
      "totalCopies": 0,
      "availableCopies": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="listbooks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of books|[BookListResponse](#schemabooklistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## createBook

<a id="opIdcreateBook"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/books \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/books HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "numberOfCopies": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/books',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/books',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/books', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/books', array(
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
URL obj = new URL("/api/books");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/books", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /books`

*Create a book*

> Body parameter

```json
{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "numberOfCopies": 0
}
```

<h3 id="createbook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BookInput](#schemabookinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "categoryName": "string",
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "totalCopies": 0,
  "availableCopies": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createbook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Book](#schemabook)|

<aside class="success">
This operation does not require authentication
</aside>

## getBook

<a id="opIdgetBook"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/books/{id} \
  -H 'Accept: application/json'

```

```http
GET /api/books/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/books/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/books/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/books/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/books/{id}', array(
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
URL obj = new URL("/api/books/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/books/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /books/{id}`

*Get book by ID with copy counts*

<h3 id="getbook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "categoryName": "string",
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "totalCopies": 0,
  "availableCopies": 0,
  "copies": [
    {
      "id": 0,
      "bookId": 0,
      "barcode": "string",
      "status": "available",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="getbook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Book detail|[BookDetail](#schemabookdetail)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateBook

<a id="opIdupdateBook"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/books/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/books/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/books/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/books/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/books/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/books/{id}', array(
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
URL obj = new URL("/api/books/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/books/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /books/{id}`

*Update a book*

> Body parameter

```json
{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string"
}
```

<h3 id="updatebook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[BookUpdate](#schemabookupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "categoryName": "string",
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "totalCopies": 0,
  "availableCopies": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updatebook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[Book](#schemabook)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteBook

<a id="opIddeleteBook"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/books/{id}

```

```http
DELETE /api/books/{id} HTTP/1.1

```

```javascript

fetch('/api/books/{id}',
{
  method: 'DELETE'

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

result = RestClient.delete '/api/books/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/api/books/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/books/{id}', array(
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
URL obj = new URL("/api/books/{id}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/books/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /books/{id}`

*Delete a book*

<h3 id="deletebook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

<h3 id="deletebook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-book-copies">book-copies</h1>

Book copy operations

## listBookCopies

<a id="opIdlistBookCopies"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/books/{bookId}/copies \
  -H 'Accept: application/json'

```

```http
GET /api/books/{bookId}/copies HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/books/{bookId}/copies',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/books/{bookId}/copies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/books/{bookId}/copies', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/books/{bookId}/copies', array(
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
URL obj = new URL("/api/books/{bookId}/copies");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/books/{bookId}/copies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /books/{bookId}/copies`

*List copies of a book*

<h3 id="listbookcopies-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bookId|path|integer|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "bookId": 0,
    "barcode": "string",
    "status": "available",
    "createdAt": "string",
    "updatedAt": "string"
  }
]
```

<h3 id="listbookcopies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of copies|Inline|

<h3 id="listbookcopies-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BookCopy](#schemabookcopy)]|false|none|none|
|» id|integer|true|none|none|
|» bookId|integer|true|none|none|
|» barcode|string|true|none|none|
|» status|string|true|none|none|
|» createdAt|string|false|none|none|
|» updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|borrowed|
|status|lost|
|status|damaged|

<aside class="success">
This operation does not require authentication
</aside>

## addBookCopy

<a id="opIdaddBookCopy"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/books/{bookId}/copies \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/books/{bookId}/copies HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "barcode": "string",
  "status": "available"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/books/{bookId}/copies',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/books/{bookId}/copies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/books/{bookId}/copies', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/books/{bookId}/copies', array(
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
URL obj = new URL("/api/books/{bookId}/copies");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/books/{bookId}/copies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /books/{bookId}/copies`

*Add a copy to a book*

> Body parameter

```json
{
  "barcode": "string",
  "status": "available"
}
```

<h3 id="addbookcopy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bookId|path|integer|true|none|
|body|body|[BookCopyInput](#schemabookcopyinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "bookId": 0,
  "barcode": "string",
  "status": "available",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="addbookcopy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[BookCopy](#schemabookcopy)|

<aside class="success">
This operation does not require authentication
</aside>

## updateBookCopy

<a id="opIdupdateBookCopy"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/copies/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/copies/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "barcode": "string",
  "status": "available"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/copies/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/copies/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/copies/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/copies/{id}', array(
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
URL obj = new URL("/api/copies/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/copies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /copies/{id}`

*Update a book copy*

> Body parameter

```json
{
  "barcode": "string",
  "status": "available"
}
```

<h3 id="updatebookcopy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[BookCopyUpdate](#schemabookcopyupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "bookId": 0,
  "barcode": "string",
  "status": "available",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updatebookcopy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[BookCopy](#schemabookcopy)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteBookCopy

<a id="opIddeleteBookCopy"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/copies/{id}

```

```http
DELETE /api/copies/{id} HTTP/1.1

```

```javascript

fetch('/api/copies/{id}',
{
  method: 'DELETE'

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

result = RestClient.delete '/api/copies/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/api/copies/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/copies/{id}', array(
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
URL obj = new URL("/api/copies/{id}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/copies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /copies/{id}`

*Delete a book copy*

<h3 id="deletebookcopy-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

<h3 id="deletebookcopy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-members">members</h1>

Library member operations

## listMembers

<a id="opIdlistMembers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/members \
  -H 'Accept: application/json'

```

```http
GET /api/members HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/members',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/members',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/members', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/members', array(
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
URL obj = new URL("/api/members");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/members", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /members`

*List members*

<h3 id="listmembers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|
|status|query|string|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|active|
|status|inactive|
|status|suspended|

> Example responses

> 200 Response

```json
{
  "members": [
    {
      "id": 0,
      "fullName": "string",
      "email": "string",
      "phone": "string",
      "address": "string",
      "membershipNumber": "string",
      "membershipStartDate": "string",
      "membershipExpiryDate": "string",
      "status": "active",
      "activeBorrows": 0,
      "outstandingFines": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="listmembers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of members|[MemberListResponse](#schemamemberlistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## createMember

<a id="opIdcreateMember"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/members \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/members HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/members',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/members',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/members', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/members', array(
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
URL obj = new URL("/api/members");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/members", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /members`

*Register a new member*

> Body parameter

```json
{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}
```

<h3 id="createmember-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MemberInput](#schemamemberinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipNumber": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active",
  "activeBorrows": 0,
  "outstandingFines": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createmember-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Member](#schemamember)|

<aside class="success">
This operation does not require authentication
</aside>

## getMember

<a id="opIdgetMember"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/members/{id} \
  -H 'Accept: application/json'

```

```http
GET /api/members/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/members/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/members/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/members/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/members/{id}', array(
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
URL obj = new URL("/api/members/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/members/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /members/{id}`

*Get member by ID with active borrows and outstanding fines*

<h3 id="getmember-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipNumber": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active",
  "activeBorrows": 0,
  "outstandingFines": 0,
  "recentBorrows": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="getmember-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Member detail|[MemberDetail](#schemamemberdetail)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateMember

<a id="opIdupdateMember"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/members/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/members/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/members/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/members/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/members/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/members/{id}', array(
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
URL obj = new URL("/api/members/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/members/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /members/{id}`

*Update a member*

> Body parameter

```json
{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}
```

<h3 id="updatemember-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[MemberUpdate](#schemamemberupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipNumber": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active",
  "activeBorrows": 0,
  "outstandingFines": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updatemember-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[Member](#schemamember)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteMember

<a id="opIddeleteMember"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/members/{id}

```

```http
DELETE /api/members/{id} HTTP/1.1

```

```javascript

fetch('/api/members/{id}',
{
  method: 'DELETE'

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

result = RestClient.delete '/api/members/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/api/members/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/members/{id}', array(
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
URL obj = new URL("/api/members/{id}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/members/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /members/{id}`

*Delete a member*

<h3 id="deletemember-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

<h3 id="deletemember-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

## fetchMemberHistory

<a id="opIdfetchMemberHistory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/members/{id}/borrowing-history \
  -H 'Accept: application/json'

```

```http
GET /api/members/{id}/borrowing-history HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/members/{id}/borrowing-history',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/members/{id}/borrowing-history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/members/{id}/borrowing-history', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/members/{id}/borrowing-history', array(
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
URL obj = new URL("/api/members/{id}/borrowing-history");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/members/{id}/borrowing-history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /members/{id}/borrowing-history`

*Get borrowing history for a member*

<h3 id="fetchmemberhistory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "transactions": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="fetchmemberhistory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Borrowing history|[BorrowingHistoryResponse](#schemaborrowinghistoryresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-borrowing">borrowing</h1>

Borrowing transaction operations

## listBorrowingTransactions

<a id="opIdlistBorrowingTransactions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/borrowing \
  -H 'Accept: application/json'

```

```http
GET /api/borrowing HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/borrowing',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/borrowing',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/borrowing', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/borrowing', array(
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
URL obj = new URL("/api/borrowing");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/borrowing", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /borrowing`

*List borrowing transactions*

<h3 id="listborrowingtransactions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|status|query|string|false|none|
|memberId|query|integer|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|borrowed|
|status|returned|
|status|overdue|
|status|all|

> Example responses

> 200 Response

```json
{
  "transactions": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="listborrowingtransactions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of borrowing transactions|[BorrowingListResponse](#schemaborrowinglistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## createBorrowingTransaction

<a id="opIdcreateBorrowingTransaction"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/borrowing \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/borrowing HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "memberId": 0,
  "copyId": 0,
  "expectedReturnDate": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/borrowing',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/borrowing',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/borrowing', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/borrowing', array(
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
URL obj = new URL("/api/borrowing");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/borrowing", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /borrowing`

*Record a book borrow*

> Body parameter

```json
{
  "memberId": 0,
  "copyId": 0,
  "expectedReturnDate": "string"
}
```

<h3 id="createborrowingtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BorrowInput](#schemaborrowinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "memberId": 0,
  "memberName": "string",
  "copyId": 0,
  "barcode": "string",
  "bookId": 0,
  "bookTitle": "string",
  "bookAuthor": "string",
  "bookCover": "string",
  "librarianId": 0,
  "librarianName": "string",
  "borrowDate": "string",
  "expectedReturnDate": "string",
  "actualReturnDate": "string",
  "status": "borrowed",
  "returnedBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createborrowingtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Borrowing transaction created|[BorrowingTransaction](#schemaborrowingtransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Copy not available or validation error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBorrowingTransaction

<a id="opIdgetBorrowingTransaction"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/borrowing/{id} \
  -H 'Accept: application/json'

```

```http
GET /api/borrowing/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/borrowing/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/borrowing/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/borrowing/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/borrowing/{id}', array(
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
URL obj = new URL("/api/borrowing/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/borrowing/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /borrowing/{id}`

*Get a borrowing transaction by ID*

<h3 id="getborrowingtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "memberId": 0,
  "memberName": "string",
  "copyId": 0,
  "barcode": "string",
  "bookId": 0,
  "bookTitle": "string",
  "bookAuthor": "string",
  "bookCover": "string",
  "librarianId": 0,
  "librarianName": "string",
  "borrowDate": "string",
  "expectedReturnDate": "string",
  "actualReturnDate": "string",
  "status": "borrowed",
  "returnedBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="getborrowingtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Borrowing transaction|[BorrowingTransaction](#schemaborrowingtransaction)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-returns">returns</h1>

Return operations

## returnBook

<a id="opIdreturnBook"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/borrowing/{id}/return \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/borrowing/{id}/return HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "actualReturnDate": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/borrowing/{id}/return',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/borrowing/{id}/return',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/borrowing/{id}/return', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/borrowing/{id}/return', array(
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
URL obj = new URL("/api/borrowing/{id}/return");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/borrowing/{id}/return", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /borrowing/{id}/return`

*Record book return and auto-calculate fine*

> Body parameter

```json
{
  "actualReturnDate": "string"
}
```

<h3 id="returnbook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[ReturnInput](#schemareturninput)|true|none|

> Example responses

> 200 Response

```json
{
  "transaction": {
    "id": 0,
    "memberId": 0,
    "memberName": "string",
    "copyId": 0,
    "barcode": "string",
    "bookId": 0,
    "bookTitle": "string",
    "bookAuthor": "string",
    "bookCover": "string",
    "librarianId": 0,
    "librarianName": "string",
    "borrowDate": "string",
    "expectedReturnDate": "string",
    "actualReturnDate": "string",
    "status": "borrowed",
    "returnedBy": 0,
    "createdAt": "string",
    "updatedAt": "string"
  },
  "lateDays": 0,
  "fineAmount": 0,
  "fineCreated": true,
  "fine": {
    "id": 0,
    "borrowingId": 0,
    "memberName": "string",
    "bookTitle": "string",
    "lateDays": 0,
    "fineAmount": 0,
    "paidStatus": "paid",
    "paidAt": "string",
    "createdAt": "string",
    "updatedAt": "string"
  }
}
```

<h3 id="returnbook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Return processed with fine info|[ReturnResult](#schemareturnresult)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-fines">fines</h1>

Fine operations

## listFines

<a id="opIdlistFines"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/fines \
  -H 'Accept: application/json'

```

```http
GET /api/fines HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/fines',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/fines',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/fines', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/fines', array(
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
URL obj = new URL("/api/fines");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/fines", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /fines`

*List all fines*

<h3 id="listfines-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paidStatus|query|string|false|none|
|memberId|query|integer|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|paidStatus|paid|
|paidStatus|unpaid|
|paidStatus|all|

> Example responses

> 200 Response

```json
{
  "fines": [
    {
      "id": 0,
      "borrowingId": 0,
      "memberName": "string",
      "bookTitle": "string",
      "lateDays": 0,
      "fineAmount": 0,
      "paidStatus": "paid",
      "paidAt": "string",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="listfines-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of fines|[FineListResponse](#schemafinelistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## payFine

<a id="opIdpayFine"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/fines/{id}/pay \
  -H 'Accept: application/json'

```

```http
POST /api/fines/{id}/pay HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/fines/{id}/pay',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/fines/{id}/pay',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/fines/{id}/pay', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/fines/{id}/pay', array(
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
URL obj = new URL("/api/fines/{id}/pay");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/fines/{id}/pay", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /fines/{id}/pay`

*Mark a fine as paid*

<h3 id="payfine-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "borrowingId": 0,
  "memberName": "string",
  "bookTitle": "string",
  "lateDays": 0,
  "fineAmount": 0,
  "paidStatus": "paid",
  "paidAt": "string",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="payfine-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Fine paid|[Fine](#schemafine)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-users">users</h1>

System user operations (admin)

## listUsers

<a id="opIdlistUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/users \
  -H 'Accept: application/json'

```

```http
GET /api/users HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/users',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/users', array(
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
URL obj = new URL("/api/users");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

*List system users (librarians and admins)*

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "clerkId": "string",
    "fullName": "string",
    "email": "string",
    "role": "admin",
    "phone": "string",
    "status": "active",
    "createdAt": "string",
    "updatedAt": "string"
  }
]
```

<h3 id="listusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of users|Inline|

<h3 id="listusers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SystemUser](#schemasystemuser)]|false|none|none|
|» id|integer|true|none|none|
|» clerkId|string,null|false|none|none|
|» fullName|string|true|none|none|
|» email|string|true|none|none|
|» role|string|true|none|none|
|» phone|string,null|false|none|none|
|» status|string|true|none|none|
|» createdAt|string|false|none|none|
|» updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|librarian|
|status|active|
|status|inactive|

<aside class="success">
This operation does not require authentication
</aside>

## createUser

<a id="opIdcreateUser"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/users HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/users',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/users', array(
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
URL obj = new URL("/api/users");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users`

*Create a system user*

> Body parameter

```json
{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string"
}
```

<h3 id="createuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserInput](#schemauserinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "clerkId": "string",
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[SystemUser](#schemasystemuser)|

<aside class="success">
This operation does not require authentication
</aside>

## updateUser

<a id="opIdupdateUser"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/users/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/users/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/users/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/users/{id}', array(
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
URL obj = new URL("/api/users/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /users/{id}`

*Update a user*

> Body parameter

```json
{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active"
}
```

<h3 id="updateuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[UserUpdate](#schemauserupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "clerkId": "string",
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updateuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[SystemUser](#schemasystemuser)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUser

<a id="opIddeleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/users/{id}

```

```http
DELETE /api/users/{id} HTTP/1.1

```

```javascript

fetch('/api/users/{id}',
{
  method: 'DELETE'

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

result = RestClient.delete '/api/users/{id}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('/api/users/{id}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/users/{id}', array(
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
URL obj = new URL("/api/users/{id}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /users/{id}`

*Delete a user*

<h3 id="deleteuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-fine-rules">fine-rules</h1>

Fine rule configuration

## listFineRules

<a id="opIdlistFineRules"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/fine-rules \
  -H 'Accept: application/json'

```

```http
GET /api/fine-rules HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/fine-rules',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/fine-rules',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/fine-rules', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/fine-rules', array(
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
URL obj = new URL("/api/fine-rules");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/fine-rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /fine-rules`

*List fine rules*

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "finePerDay": 0,
    "maxFine": 0,
    "createdBy": 0,
    "createdAt": "string",
    "updatedAt": "string"
  }
]
```

<h3 id="listfinerules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Fine rules|Inline|

<h3 id="listfinerules-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[FineRule](#schemafinerule)]|false|none|none|
|» id|integer|true|none|none|
|» finePerDay|number|true|none|none|
|» maxFine|number,null|false|none|none|
|» createdBy|integer,null|false|none|none|
|» createdAt|string|false|none|none|
|» updatedAt|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## createFineRule

<a id="opIdcreateFineRule"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/fine-rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/fine-rules HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "finePerDay": 0,
  "maxFine": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/fine-rules',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/fine-rules',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/fine-rules', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/fine-rules', array(
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
URL obj = new URL("/api/fine-rules");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/fine-rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /fine-rules`

*Create a fine rule*

> Body parameter

```json
{
  "finePerDay": 0,
  "maxFine": 0
}
```

<h3 id="createfinerule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FineRuleInput](#schemafineruleinput)|true|none|

> Example responses

> 201 Response

```json
{
  "id": 0,
  "finePerDay": 0,
  "maxFine": 0,
  "createdBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="createfinerule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[FineRule](#schemafinerule)|

<aside class="success">
This operation does not require authentication
</aside>

## updateFineRule

<a id="opIdupdateFineRule"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/fine-rules/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /api/fine-rules/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "finePerDay": 0,
  "maxFine": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/fine-rules/{id}',
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
  'Accept' => 'application/json'
}

result = RestClient.patch '/api/fine-rules/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/fine-rules/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/fine-rules/{id}', array(
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
URL obj = new URL("/api/fine-rules/{id}");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/fine-rules/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /fine-rules/{id}`

*Update a fine rule*

> Body parameter

```json
{
  "finePerDay": 0,
  "maxFine": 0
}
```

<h3 id="updatefinerule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|none|
|body|body|[FineRuleUpdate](#schemafineruleupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "finePerDay": 0,
  "maxFine": 0,
  "createdBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="updatefinerule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated|[FineRule](#schemafinerule)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-settings">settings</h1>

System settings

## listSettings

<a id="opIdlistSettings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/settings \
  -H 'Accept: application/json'

```

```http
GET /api/settings HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/settings',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/settings', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/settings', array(
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
URL obj = new URL("/api/settings");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /settings`

*Get all settings*

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "settingKey": "string",
    "settingValue": "string",
    "createdAt": "string",
    "updatedAt": "string"
  }
]
```

<h3 id="listsettings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Settings list|Inline|

<h3 id="listsettings-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Setting](#schemasetting)]|false|none|none|
|» id|integer|true|none|none|
|» settingKey|string|true|none|none|
|» settingValue|string|true|none|none|
|» createdAt|string|false|none|none|
|» updatedAt|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## upsertSetting

<a id="opIdupsertSetting"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /api/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /api/settings HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "settingKey": "string",
  "settingValue": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/api/settings',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/api/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/settings', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/settings', array(
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
URL obj = new URL("/api/settings");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /settings`

*Create or update a setting*

> Body parameter

```json
{
  "settingKey": "string",
  "settingValue": "string"
}
```

<h3 id="upsertsetting-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SettingInput](#schemasettinginput)|true|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "settingKey": "string",
  "settingValue": "string",
  "createdAt": "string",
  "updatedAt": "string"
}
```

<h3 id="upsertsetting-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Upserted|[Setting](#schemasetting)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-reports">reports</h1>

Reports and analytics

## getDashboardStats

<a id="opIdgetDashboardStats"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/reports/dashboard \
  -H 'Accept: application/json'

```

```http
GET /api/reports/dashboard HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/reports/dashboard',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/reports/dashboard',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/reports/dashboard', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/reports/dashboard', array(
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
URL obj = new URL("/api/reports/dashboard");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/reports/dashboard", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /reports/dashboard`

*Get dashboard statistics*

> Example responses

> 200 Response

```json
{
  "totalBooks": 0,
  "totalCopies": 0,
  "availableCopies": 0,
  "borrowedCopies": 0,
  "overdueBooks": 0,
  "outstandingFines": 0,
  "totalMembers": 0,
  "activeMembers": 0,
  "recentBorrowings": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ]
}
```

<h3 id="getdashboardstats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Dashboard stats|[DashboardStats](#schemadashboardstats)|

<aside class="success">
This operation does not require authentication
</aside>

## getOverdueBooks

<a id="opIdgetOverdueBooks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/reports/overdue \
  -H 'Accept: application/json'

```

```http
GET /api/reports/overdue HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/reports/overdue',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/reports/overdue',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/reports/overdue', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/reports/overdue', array(
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
URL obj = new URL("/api/reports/overdue");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/reports/overdue", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /reports/overdue`

*Get overdue books with fine amounts*

<h3 id="getoverduebooks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|none|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "transactionId": 0,
      "memberId": 0,
      "memberName": "string",
      "bookTitle": "string",
      "bookAuthor": "string",
      "barcode": "string",
      "expectedReturnDate": "string",
      "daysOverdue": 0,
      "estimatedFine": 0
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="getoverduebooks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Overdue books|[OverdueListResponse](#schemaoverduelistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## getMostBorrowedBooks

<a id="opIdgetMostBorrowedBooks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/reports/most-borrowed \
  -H 'Accept: application/json'

```

```http
GET /api/reports/most-borrowed HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/reports/most-borrowed',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/reports/most-borrowed',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/reports/most-borrowed', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/reports/most-borrowed', array(
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
URL obj = new URL("/api/reports/most-borrowed");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/reports/most-borrowed", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /reports/most-borrowed`

*Get most borrowed books*

<h3 id="getmostborrowedbooks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
[
  {
    "bookId": 0,
    "title": "string",
    "author": "string",
    "categoryName": "string",
    "coverImage": "string",
    "borrowCount": 0
  }
]
```

<h3 id="getmostborrowedbooks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Most borrowed books|Inline|

<h3 id="getmostborrowedbooks-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[MostBorrowedBook](#schemamostborrowedbook)]|false|none|none|
|» bookId|integer|true|none|none|
|» title|string|true|none|none|
|» author|string|true|none|none|
|» categoryName|string,null|false|none|none|
|» coverImage|string,null|false|none|none|
|» borrowCount|integer|true|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getMemberActivity

<a id="opIdgetMemberActivity"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/reports/member-activity \
  -H 'Accept: application/json'

```

```http
GET /api/reports/member-activity HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/reports/member-activity',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/reports/member-activity',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/reports/member-activity', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/reports/member-activity', array(
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
URL obj = new URL("/api/reports/member-activity");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/reports/member-activity", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /reports/member-activity`

*Get member activity report*

<h3 id="getmemberactivity-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
[
  {
    "memberId": 0,
    "memberName": "string",
    "email": "string",
    "totalBorrows": 0,
    "activeBorrows": 0,
    "outstandingFines": 0
  }
]
```

<h3 id="getmemberactivity-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Member activity|Inline|

<h3 id="getmemberactivity-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[MemberActivity](#schemamemberactivity)]|false|none|none|
|» memberId|integer|true|none|none|
|» memberName|string|true|none|none|
|» email|string|false|none|none|
|» totalBorrows|integer|true|none|none|
|» activeBorrows|integer|true|none|none|
|» outstandingFines|number|true|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="api-audit-logs">audit-logs</h1>

Audit log operations

## listAuditLogs

<a id="opIdlistAuditLogs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /api/audit-logs \
  -H 'Accept: application/json'

```

```http
GET /api/audit-logs HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/api/audit-logs',
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
  'Accept' => 'application/json'
}

result = RestClient.get '/api/audit-logs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/audit-logs', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/audit-logs', array(
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
URL obj = new URL("/api/audit-logs");
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
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/audit-logs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /audit-logs`

*List audit logs*

<h3 id="listauditlogs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|entityName|query|string|false|none|
|userId|query|integer|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|

> Example responses

> 200 Response

```json
{
  "logs": [
    {
      "id": 0,
      "userId": 0,
      "userName": "string",
      "action": "string",
      "entityName": "string",
      "entityId": 0,
      "details": "string",
      "createdAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}
```

<h3 id="listauditlogs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Audit logs|[AuditLogListResponse](#schemaauditloglistresponse)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_HealthStatus">HealthStatus</h2>
<!-- backwards compatibility -->
<a id="schemahealthstatus"></a>
<a id="schema_HealthStatus"></a>
<a id="tocShealthstatus"></a>
<a id="tocshealthstatus"></a>

```json
{
  "status": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|true|none|none|

<h2 id="tocS_UserProfile">UserProfile</h2>
<!-- backwards compatibility -->
<a id="schemauserprofile"></a>
<a id="schema_UserProfile"></a>
<a id="tocSuserprofile"></a>
<a id="tocsuserprofile"></a>

```json
{
  "id": 0,
  "clerkId": "string",
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "status": "string",
  "phone": "string",
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|clerkId|string|false|none|none|
|fullName|string|true|none|none|
|email|string|true|none|none|
|role|string|true|none|none|
|status|string|false|none|none|
|phone|string,null|false|none|none|
|createdAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|librarian|

<h2 id="tocS_Category">Category</h2>
<!-- backwards compatibility -->
<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

```json
{
  "id": 0,
  "categoryName": "string",
  "description": "string",
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|categoryName|string|true|none|none|
|description|string,null|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_CategoryInput">CategoryInput</h2>
<!-- backwards compatibility -->
<a id="schemacategoryinput"></a>
<a id="schema_CategoryInput"></a>
<a id="tocScategoryinput"></a>
<a id="tocscategoryinput"></a>

```json
{
  "categoryName": "string",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categoryName|string|true|none|none|
|description|string|false|none|none|

<h2 id="tocS_CategoryUpdate">CategoryUpdate</h2>
<!-- backwards compatibility -->
<a id="schemacategoryupdate"></a>
<a id="schema_CategoryUpdate"></a>
<a id="tocScategoryupdate"></a>
<a id="tocscategoryupdate"></a>

```json
{
  "categoryName": "string",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categoryName|string|false|none|none|
|description|string|false|none|none|

<h2 id="tocS_Book">Book</h2>
<!-- backwards compatibility -->
<a id="schemabook"></a>
<a id="schema_Book"></a>
<a id="tocSbook"></a>
<a id="tocsbook"></a>

```json
{
  "id": 0,
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "categoryName": "string",
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "totalCopies": 0,
  "availableCopies": 0,
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|title|string|true|none|none|
|author|string|true|none|none|
|isbn|string,null|false|none|none|
|publisher|string,null|false|none|none|
|publicationYear|integer,null|false|none|none|
|categoryId|integer,null|false|none|none|
|categoryName|string,null|false|none|none|
|shelfLocation|string,null|false|none|none|
|description|string,null|false|none|none|
|coverImage|string,null|false|none|none|
|totalCopies|integer|false|none|none|
|availableCopies|integer|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_BookDetail">BookDetail</h2>
<!-- backwards compatibility -->
<a id="schemabookdetail"></a>
<a id="schema_BookDetail"></a>
<a id="tocSbookdetail"></a>
<a id="tocsbookdetail"></a>

```json
{
  "id": 0,
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "categoryName": "string",
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "totalCopies": 0,
  "availableCopies": 0,
  "copies": [
    {
      "id": 0,
      "bookId": 0,
      "barcode": "string",
      "status": "available",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|title|string|true|none|none|
|author|string|true|none|none|
|isbn|string,null|false|none|none|
|publisher|string,null|false|none|none|
|publicationYear|integer,null|false|none|none|
|categoryId|integer,null|false|none|none|
|categoryName|string,null|false|none|none|
|shelfLocation|string,null|false|none|none|
|description|string,null|false|none|none|
|coverImage|string,null|false|none|none|
|totalCopies|integer|false|none|none|
|availableCopies|integer|false|none|none|
|copies|[[BookCopy](#schemabookcopy)]|true|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_BookInput">BookInput</h2>
<!-- backwards compatibility -->
<a id="schemabookinput"></a>
<a id="schema_BookInput"></a>
<a id="tocSbookinput"></a>
<a id="tocsbookinput"></a>

```json
{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string",
  "numberOfCopies": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|true|none|none|
|author|string|true|none|none|
|isbn|string|false|none|none|
|publisher|string|false|none|none|
|publicationYear|integer|false|none|none|
|categoryId|integer|false|none|none|
|shelfLocation|string|false|none|none|
|description|string|false|none|none|
|coverImage|string|false|none|none|
|numberOfCopies|integer|false|none|none|

<h2 id="tocS_BookUpdate">BookUpdate</h2>
<!-- backwards compatibility -->
<a id="schemabookupdate"></a>
<a id="schema_BookUpdate"></a>
<a id="tocSbookupdate"></a>
<a id="tocsbookupdate"></a>

```json
{
  "title": "string",
  "author": "string",
  "isbn": "string",
  "publisher": "string",
  "publicationYear": 0,
  "categoryId": 0,
  "shelfLocation": "string",
  "description": "string",
  "coverImage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|author|string|false|none|none|
|isbn|string|false|none|none|
|publisher|string|false|none|none|
|publicationYear|integer|false|none|none|
|categoryId|integer|false|none|none|
|shelfLocation|string|false|none|none|
|description|string|false|none|none|
|coverImage|string|false|none|none|

<h2 id="tocS_BookListResponse">BookListResponse</h2>
<!-- backwards compatibility -->
<a id="schemabooklistresponse"></a>
<a id="schema_BookListResponse"></a>
<a id="tocSbooklistresponse"></a>
<a id="tocsbooklistresponse"></a>

```json
{
  "books": [
    {
      "id": 0,
      "title": "string",
      "author": "string",
      "isbn": "string",
      "publisher": "string",
      "publicationYear": 0,
      "categoryId": 0,
      "categoryName": "string",
      "shelfLocation": "string",
      "description": "string",
      "coverImage": "string",
      "totalCopies": 0,
      "availableCopies": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|books|[[Book](#schemabook)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_BookCopy">BookCopy</h2>
<!-- backwards compatibility -->
<a id="schemabookcopy"></a>
<a id="schema_BookCopy"></a>
<a id="tocSbookcopy"></a>
<a id="tocsbookcopy"></a>

```json
{
  "id": 0,
  "bookId": 0,
  "barcode": "string",
  "status": "available",
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|bookId|integer|true|none|none|
|barcode|string|true|none|none|
|status|string|true|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|borrowed|
|status|lost|
|status|damaged|

<h2 id="tocS_BookCopyInput">BookCopyInput</h2>
<!-- backwards compatibility -->
<a id="schemabookcopyinput"></a>
<a id="schema_BookCopyInput"></a>
<a id="tocSbookcopyinput"></a>
<a id="tocsbookcopyinput"></a>

```json
{
  "barcode": "string",
  "status": "available"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|barcode|string|true|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|borrowed|
|status|lost|
|status|damaged|

<h2 id="tocS_BookCopyUpdate">BookCopyUpdate</h2>
<!-- backwards compatibility -->
<a id="schemabookcopyupdate"></a>
<a id="schema_BookCopyUpdate"></a>
<a id="tocSbookcopyupdate"></a>
<a id="tocsbookcopyupdate"></a>

```json
{
  "barcode": "string",
  "status": "available"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|barcode|string|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|borrowed|
|status|lost|
|status|damaged|

<h2 id="tocS_Member">Member</h2>
<!-- backwards compatibility -->
<a id="schemamember"></a>
<a id="schema_Member"></a>
<a id="tocSmember"></a>
<a id="tocsmember"></a>

```json
{
  "id": 0,
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipNumber": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active",
  "activeBorrows": 0,
  "outstandingFines": 0,
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|fullName|string|true|none|none|
|email|string|true|none|none|
|phone|string,null|false|none|none|
|address|string,null|false|none|none|
|membershipNumber|string|true|none|none|
|membershipStartDate|string,null|false|none|none|
|membershipExpiryDate|string,null|false|none|none|
|status|string|false|none|none|
|activeBorrows|integer|false|none|none|
|outstandingFines|number|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|active|
|status|inactive|
|status|suspended|

<h2 id="tocS_MemberDetail">MemberDetail</h2>
<!-- backwards compatibility -->
<a id="schemamemberdetail"></a>
<a id="schema_MemberDetail"></a>
<a id="tocSmemberdetail"></a>
<a id="tocsmemberdetail"></a>

```json
{
  "id": 0,
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipNumber": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active",
  "activeBorrows": 0,
  "outstandingFines": 0,
  "recentBorrows": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|fullName|string|true|none|none|
|email|string|true|none|none|
|phone|string,null|false|none|none|
|address|string,null|false|none|none|
|membershipNumber|string|true|none|none|
|membershipStartDate|string,null|false|none|none|
|membershipExpiryDate|string,null|false|none|none|
|status|string|false|none|none|
|activeBorrows|integer|false|none|none|
|outstandingFines|number|false|none|none|
|recentBorrows|[[BorrowingTransaction](#schemaborrowingtransaction)]|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|active|
|status|inactive|
|status|suspended|

<h2 id="tocS_MemberInput">MemberInput</h2>
<!-- backwards compatibility -->
<a id="schemamemberinput"></a>
<a id="schema_MemberInput"></a>
<a id="tocSmemberinput"></a>
<a id="tocsmemberinput"></a>

```json
{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fullName|string|true|none|none|
|email|string|true|none|none|
|phone|string|false|none|none|
|address|string|false|none|none|
|membershipStartDate|string|false|none|none|
|membershipExpiryDate|string|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|active|
|status|inactive|
|status|suspended|

<h2 id="tocS_MemberUpdate">MemberUpdate</h2>
<!-- backwards compatibility -->
<a id="schemamemberupdate"></a>
<a id="schema_MemberUpdate"></a>
<a id="tocSmemberupdate"></a>
<a id="tocsmemberupdate"></a>

```json
{
  "fullName": "string",
  "email": "string",
  "phone": "string",
  "address": "string",
  "membershipStartDate": "string",
  "membershipExpiryDate": "string",
  "status": "active"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fullName|string|false|none|none|
|email|string|false|none|none|
|phone|string|false|none|none|
|address|string|false|none|none|
|membershipStartDate|string|false|none|none|
|membershipExpiryDate|string|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|active|
|status|inactive|
|status|suspended|

<h2 id="tocS_MemberListResponse">MemberListResponse</h2>
<!-- backwards compatibility -->
<a id="schemamemberlistresponse"></a>
<a id="schema_MemberListResponse"></a>
<a id="tocSmemberlistresponse"></a>
<a id="tocsmemberlistresponse"></a>

```json
{
  "members": [
    {
      "id": 0,
      "fullName": "string",
      "email": "string",
      "phone": "string",
      "address": "string",
      "membershipNumber": "string",
      "membershipStartDate": "string",
      "membershipExpiryDate": "string",
      "status": "active",
      "activeBorrows": 0,
      "outstandingFines": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|members|[[Member](#schemamember)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_BorrowingTransaction">BorrowingTransaction</h2>
<!-- backwards compatibility -->
<a id="schemaborrowingtransaction"></a>
<a id="schema_BorrowingTransaction"></a>
<a id="tocSborrowingtransaction"></a>
<a id="tocsborrowingtransaction"></a>

```json
{
  "id": 0,
  "memberId": 0,
  "memberName": "string",
  "copyId": 0,
  "barcode": "string",
  "bookId": 0,
  "bookTitle": "string",
  "bookAuthor": "string",
  "bookCover": "string",
  "librarianId": 0,
  "librarianName": "string",
  "borrowDate": "string",
  "expectedReturnDate": "string",
  "actualReturnDate": "string",
  "status": "borrowed",
  "returnedBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|memberId|integer|true|none|none|
|memberName|string,null|false|none|none|
|copyId|integer|true|none|none|
|barcode|string,null|false|none|none|
|bookId|integer,null|false|none|none|
|bookTitle|string,null|false|none|none|
|bookAuthor|string,null|false|none|none|
|bookCover|string,null|false|none|none|
|librarianId|integer,null|false|none|none|
|librarianName|string,null|false|none|none|
|borrowDate|string|true|none|none|
|expectedReturnDate|string|true|none|none|
|actualReturnDate|string,null|false|none|none|
|status|string|true|none|none|
|returnedBy|integer,null|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|borrowed|
|status|returned|
|status|overdue|

<h2 id="tocS_BorrowInput">BorrowInput</h2>
<!-- backwards compatibility -->
<a id="schemaborrowinput"></a>
<a id="schema_BorrowInput"></a>
<a id="tocSborrowinput"></a>
<a id="tocsborrowinput"></a>

```json
{
  "memberId": 0,
  "copyId": 0,
  "expectedReturnDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|memberId|integer|true|none|none|
|copyId|integer|true|none|none|
|expectedReturnDate|string|true|none|none|

<h2 id="tocS_BorrowingListResponse">BorrowingListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaborrowinglistresponse"></a>
<a id="schema_BorrowingListResponse"></a>
<a id="tocSborrowinglistresponse"></a>
<a id="tocsborrowinglistresponse"></a>

```json
{
  "transactions": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactions|[[BorrowingTransaction](#schemaborrowingtransaction)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_BorrowingHistoryResponse">BorrowingHistoryResponse</h2>
<!-- backwards compatibility -->
<a id="schemaborrowinghistoryresponse"></a>
<a id="schema_BorrowingHistoryResponse"></a>
<a id="tocSborrowinghistoryresponse"></a>
<a id="tocsborrowinghistoryresponse"></a>

```json
{
  "transactions": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactions|[[BorrowingTransaction](#schemaborrowingtransaction)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_ReturnInput">ReturnInput</h2>
<!-- backwards compatibility -->
<a id="schemareturninput"></a>
<a id="schema_ReturnInput"></a>
<a id="tocSreturninput"></a>
<a id="tocsreturninput"></a>

```json
{
  "actualReturnDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|actualReturnDate|string|true|none|none|

<h2 id="tocS_ReturnResult">ReturnResult</h2>
<!-- backwards compatibility -->
<a id="schemareturnresult"></a>
<a id="schema_ReturnResult"></a>
<a id="tocSreturnresult"></a>
<a id="tocsreturnresult"></a>

```json
{
  "transaction": {
    "id": 0,
    "memberId": 0,
    "memberName": "string",
    "copyId": 0,
    "barcode": "string",
    "bookId": 0,
    "bookTitle": "string",
    "bookAuthor": "string",
    "bookCover": "string",
    "librarianId": 0,
    "librarianName": "string",
    "borrowDate": "string",
    "expectedReturnDate": "string",
    "actualReturnDate": "string",
    "status": "borrowed",
    "returnedBy": 0,
    "createdAt": "string",
    "updatedAt": "string"
  },
  "lateDays": 0,
  "fineAmount": 0,
  "fineCreated": true,
  "fine": {
    "id": 0,
    "borrowingId": 0,
    "memberName": "string",
    "bookTitle": "string",
    "lateDays": 0,
    "fineAmount": 0,
    "paidStatus": "paid",
    "paidAt": "string",
    "createdAt": "string",
    "updatedAt": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transaction|[BorrowingTransaction](#schemaborrowingtransaction)|true|none|none|
|lateDays|integer|true|none|none|
|fineAmount|number|true|none|none|
|fineCreated|boolean|true|none|none|
|fine|[Fine](#schemafine)|false|none|none|

<h2 id="tocS_Fine">Fine</h2>
<!-- backwards compatibility -->
<a id="schemafine"></a>
<a id="schema_Fine"></a>
<a id="tocSfine"></a>
<a id="tocsfine"></a>

```json
{
  "id": 0,
  "borrowingId": 0,
  "memberName": "string",
  "bookTitle": "string",
  "lateDays": 0,
  "fineAmount": 0,
  "paidStatus": "paid",
  "paidAt": "string",
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|borrowingId|integer|true|none|none|
|memberName|string,null|false|none|none|
|bookTitle|string,null|false|none|none|
|lateDays|integer|true|none|none|
|fineAmount|number|true|none|none|
|paidStatus|string|true|none|none|
|paidAt|string,null|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|paidStatus|paid|
|paidStatus|unpaid|

<h2 id="tocS_FineListResponse">FineListResponse</h2>
<!-- backwards compatibility -->
<a id="schemafinelistresponse"></a>
<a id="schema_FineListResponse"></a>
<a id="tocSfinelistresponse"></a>
<a id="tocsfinelistresponse"></a>

```json
{
  "fines": [
    {
      "id": 0,
      "borrowingId": 0,
      "memberName": "string",
      "bookTitle": "string",
      "lateDays": 0,
      "fineAmount": 0,
      "paidStatus": "paid",
      "paidAt": "string",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fines|[[Fine](#schemafine)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_FineRule">FineRule</h2>
<!-- backwards compatibility -->
<a id="schemafinerule"></a>
<a id="schema_FineRule"></a>
<a id="tocSfinerule"></a>
<a id="tocsfinerule"></a>

```json
{
  "id": 0,
  "finePerDay": 0,
  "maxFine": 0,
  "createdBy": 0,
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|finePerDay|number|true|none|none|
|maxFine|number,null|false|none|none|
|createdBy|integer,null|false|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_FineRuleInput">FineRuleInput</h2>
<!-- backwards compatibility -->
<a id="schemafineruleinput"></a>
<a id="schema_FineRuleInput"></a>
<a id="tocSfineruleinput"></a>
<a id="tocsfineruleinput"></a>

```json
{
  "finePerDay": 0,
  "maxFine": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|finePerDay|number|true|none|none|
|maxFine|number|false|none|none|

<h2 id="tocS_FineRuleUpdate">FineRuleUpdate</h2>
<!-- backwards compatibility -->
<a id="schemafineruleupdate"></a>
<a id="schema_FineRuleUpdate"></a>
<a id="tocSfineruleupdate"></a>
<a id="tocsfineruleupdate"></a>

```json
{
  "finePerDay": 0,
  "maxFine": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|finePerDay|number|false|none|none|
|maxFine|number|false|none|none|

<h2 id="tocS_SystemUser">SystemUser</h2>
<!-- backwards compatibility -->
<a id="schemasystemuser"></a>
<a id="schema_SystemUser"></a>
<a id="tocSsystemuser"></a>
<a id="tocssystemuser"></a>

```json
{
  "id": 0,
  "clerkId": "string",
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active",
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|clerkId|string,null|false|none|none|
|fullName|string|true|none|none|
|email|string|true|none|none|
|role|string|true|none|none|
|phone|string,null|false|none|none|
|status|string|true|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|librarian|
|status|active|
|status|inactive|

<h2 id="tocS_UserInput">UserInput</h2>
<!-- backwards compatibility -->
<a id="schemauserinput"></a>
<a id="schema_UserInput"></a>
<a id="tocSuserinput"></a>
<a id="tocsuserinput"></a>

```json
{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fullName|string|true|none|none|
|email|string|true|none|none|
|role|string|true|none|none|
|phone|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|librarian|

<h2 id="tocS_UserUpdate">UserUpdate</h2>
<!-- backwards compatibility -->
<a id="schemauserupdate"></a>
<a id="schema_UserUpdate"></a>
<a id="tocSuserupdate"></a>
<a id="tocsuserupdate"></a>

```json
{
  "fullName": "string",
  "email": "string",
  "role": "admin",
  "phone": "string",
  "status": "active"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fullName|string|false|none|none|
|email|string|false|none|none|
|role|string|false|none|none|
|phone|string|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|librarian|
|status|active|
|status|inactive|

<h2 id="tocS_Setting">Setting</h2>
<!-- backwards compatibility -->
<a id="schemasetting"></a>
<a id="schema_Setting"></a>
<a id="tocSsetting"></a>
<a id="tocssetting"></a>

```json
{
  "id": 0,
  "settingKey": "string",
  "settingValue": "string",
  "createdAt": "string",
  "updatedAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|settingKey|string|true|none|none|
|settingValue|string|true|none|none|
|createdAt|string|false|none|none|
|updatedAt|string|false|none|none|

<h2 id="tocS_SettingInput">SettingInput</h2>
<!-- backwards compatibility -->
<a id="schemasettinginput"></a>
<a id="schema_SettingInput"></a>
<a id="tocSsettinginput"></a>
<a id="tocssettinginput"></a>

```json
{
  "settingKey": "string",
  "settingValue": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|settingKey|string|true|none|none|
|settingValue|string|true|none|none|

<h2 id="tocS_DashboardStats">DashboardStats</h2>
<!-- backwards compatibility -->
<a id="schemadashboardstats"></a>
<a id="schema_DashboardStats"></a>
<a id="tocSdashboardstats"></a>
<a id="tocsdashboardstats"></a>

```json
{
  "totalBooks": 0,
  "totalCopies": 0,
  "availableCopies": 0,
  "borrowedCopies": 0,
  "overdueBooks": 0,
  "outstandingFines": 0,
  "totalMembers": 0,
  "activeMembers": 0,
  "recentBorrowings": [
    {
      "id": 0,
      "memberId": 0,
      "memberName": "string",
      "copyId": 0,
      "barcode": "string",
      "bookId": 0,
      "bookTitle": "string",
      "bookAuthor": "string",
      "bookCover": "string",
      "librarianId": 0,
      "librarianName": "string",
      "borrowDate": "string",
      "expectedReturnDate": "string",
      "actualReturnDate": "string",
      "status": "borrowed",
      "returnedBy": 0,
      "createdAt": "string",
      "updatedAt": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalBooks|integer|true|none|none|
|totalCopies|integer|true|none|none|
|availableCopies|integer|true|none|none|
|borrowedCopies|integer|true|none|none|
|overdueBooks|integer|true|none|none|
|outstandingFines|number|true|none|none|
|totalMembers|integer|true|none|none|
|activeMembers|integer|true|none|none|
|recentBorrowings|[[BorrowingTransaction](#schemaborrowingtransaction)]|false|none|none|

<h2 id="tocS_OverdueItem">OverdueItem</h2>
<!-- backwards compatibility -->
<a id="schemaoverdueitem"></a>
<a id="schema_OverdueItem"></a>
<a id="tocSoverdueitem"></a>
<a id="tocsoverdueitem"></a>

```json
{
  "transactionId": 0,
  "memberId": 0,
  "memberName": "string",
  "bookTitle": "string",
  "bookAuthor": "string",
  "barcode": "string",
  "expectedReturnDate": "string",
  "daysOverdue": 0,
  "estimatedFine": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactionId|integer|true|none|none|
|memberId|integer|true|none|none|
|memberName|string|true|none|none|
|bookTitle|string|true|none|none|
|bookAuthor|string,null|false|none|none|
|barcode|string|false|none|none|
|expectedReturnDate|string|true|none|none|
|daysOverdue|integer|true|none|none|
|estimatedFine|number|false|none|none|

<h2 id="tocS_OverdueListResponse">OverdueListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaoverduelistresponse"></a>
<a id="schema_OverdueListResponse"></a>
<a id="tocSoverduelistresponse"></a>
<a id="tocsoverduelistresponse"></a>

```json
{
  "items": [
    {
      "transactionId": 0,
      "memberId": 0,
      "memberName": "string",
      "bookTitle": "string",
      "bookAuthor": "string",
      "barcode": "string",
      "expectedReturnDate": "string",
      "daysOverdue": 0,
      "estimatedFine": 0
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[OverdueItem](#schemaoverdueitem)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

<h2 id="tocS_MostBorrowedBook">MostBorrowedBook</h2>
<!-- backwards compatibility -->
<a id="schemamostborrowedbook"></a>
<a id="schema_MostBorrowedBook"></a>
<a id="tocSmostborrowedbook"></a>
<a id="tocsmostborrowedbook"></a>

```json
{
  "bookId": 0,
  "title": "string",
  "author": "string",
  "categoryName": "string",
  "coverImage": "string",
  "borrowCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bookId|integer|true|none|none|
|title|string|true|none|none|
|author|string|true|none|none|
|categoryName|string,null|false|none|none|
|coverImage|string,null|false|none|none|
|borrowCount|integer|true|none|none|

<h2 id="tocS_MemberActivity">MemberActivity</h2>
<!-- backwards compatibility -->
<a id="schemamemberactivity"></a>
<a id="schema_MemberActivity"></a>
<a id="tocSmemberactivity"></a>
<a id="tocsmemberactivity"></a>

```json
{
  "memberId": 0,
  "memberName": "string",
  "email": "string",
  "totalBorrows": 0,
  "activeBorrows": 0,
  "outstandingFines": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|memberId|integer|true|none|none|
|memberName|string|true|none|none|
|email|string|false|none|none|
|totalBorrows|integer|true|none|none|
|activeBorrows|integer|true|none|none|
|outstandingFines|number|true|none|none|

<h2 id="tocS_AuditLog">AuditLog</h2>
<!-- backwards compatibility -->
<a id="schemaauditlog"></a>
<a id="schema_AuditLog"></a>
<a id="tocSauditlog"></a>
<a id="tocsauditlog"></a>

```json
{
  "id": 0,
  "userId": 0,
  "userName": "string",
  "action": "string",
  "entityName": "string",
  "entityId": 0,
  "details": "string",
  "createdAt": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|true|none|none|
|userId|integer,null|false|none|none|
|userName|string,null|false|none|none|
|action|string|true|none|none|
|entityName|string|true|none|none|
|entityId|integer,null|false|none|none|
|details|string,null|false|none|none|
|createdAt|string|true|none|none|

<h2 id="tocS_AuditLogListResponse">AuditLogListResponse</h2>
<!-- backwards compatibility -->
<a id="schemaauditloglistresponse"></a>
<a id="schema_AuditLogListResponse"></a>
<a id="tocSauditloglistresponse"></a>
<a id="tocsauditloglistresponse"></a>

```json
{
  "logs": [
    {
      "id": 0,
      "userId": 0,
      "userName": "string",
      "action": "string",
      "entityName": "string",
      "entityId": 0,
      "details": "string",
      "createdAt": "string"
    }
  ],
  "total": 0,
  "page": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logs|[[AuditLog](#schemaauditlog)]|true|none|none|
|total|integer|true|none|none|
|page|integer|true|none|none|
|limit|integer|true|none|none|

