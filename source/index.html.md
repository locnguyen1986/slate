---
title: SellRBX API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript
  - java

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://https://sellrbx.com/'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the SellRBX API
---

# Introduction

Welcome to the SellRBX API! You can use our API tol list the account you want to sell from by uploading your .ROBLOSECURITY cookie. This cookie is used so we can send R$ from your account. You can list up to 20+ cookies and delist them at any time

Once your account is listed, R$ will begin to be paid from your account. For every R$ sold, you will receive money in your balance.

Withdraw your balance to PayPal, Venmo, Cashapp, or Crypto. All crypto payments will be sent instantly after withdrawing. Other payments will be sent swiftly after you withdraw.

# Authentication

> To authorize, use this code:

```ruby
require 'SellRBX'

api = SellRBX::APIClient.authorize!('meowmeowmeow')
```

```python
import SellRBX

api = SellRBX.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const SellRBX = require('SellRBX');

let api = SellRBX.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

SellRBX uses API keys to allow access to the API. You can register a new SellRBX API key at our [developer portal](http://example.com/developers).

SellRBX expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'SellRBX'

api = SellRBX::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import SellRBX

api = SellRBX.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const SellRBX = require('SellRBX');

let api = SellRBX.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'SellRBX'

api = SellRBX::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import SellRBX

api = SellRBX.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const SellRBX = require('SellRBX');

let api = SellRBX.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'SellRBX'

api = SellRBX::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import SellRBX

api = SellRBX.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const SellRBX = require('SellRBX');

let api = SellRBX.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

