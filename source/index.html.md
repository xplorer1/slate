---
title: Vpay API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Vpay offers a range of services that make it possible for you to send and receive money across the world in minutes. On this page, we'll go over some of the payment services we offer to give you a quick overview of what is obtainable with Vpay.

Payment collection
If you're a business owner, here are a few ways we make it possible for you to collect payments from customers all over the world:

Card Payments - Customers can supply their card details and complete payment in a few minutes

Direct bank account payments (Nigeria) - Customers can pay you directly from their bank accounts.

Bank account payments (UK) - Your customers in the UK can pay directly into your Vpay account

Here's a list of countries where Vpay supports mobile money wallet collections
Ghana

Uganda

Zambia

Rwanda

Mpesa

You can also take a look at our Payment Methods for a closer look at all the possible channels through which you can receive payments from your customers using Vpay.

Tokenised Payments
This is a feature that allows you to save a customer object on your platform so your users don't have to enter their card information repeatedly.

Charge with token
Pre-authorisation
Preauthorizing a card or an account allows you to place a hold on the amount you would like to charge a customer. For instance, you can preauthorize a card for 7days before taking the money from the customer. Merchants in the Hotel, Shared economy (Uber), and flight booking industry use this to put a customer's payment on hold while they confirm value has been given.

Preauthorise a card
Transfers
With Vpay, you can make transfers to over 6+ African countries. This is a growing list that currently includes the US and Europe. We offer this feature via the dashboard and also via API for financial service providers, merchants, marketplaces, and IMTOs, etc.

How Transfers work
Bill payments
With Vpay, you can aggregate bill services such as airtime purchases and DSTV subscriptions. You get a commission for each sale and you can view your reports on a dashboard.

Bill payments
Manage Subscriptions
You can make use of our APIs to manage your customer's subscriptions for recurring payments.
Subscriptions allow you to subscribe your customers to a payment plan that will ensure recurring payments happen on their accounts following your predefined specifications.

Payment plans
Collect payments using subaccounts
You can use our APIs to manage marketplace accounts or collect payments on behalf of merchants you create on our platform. This will allow you to perform functions like edit their details, delete them and get a list of the merchants and their IDs.

Subaccounts
Other Features
You can find comprehensive documentation of all the amazing features we offer in our Vpay features section where we discuss every feature in detail.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

## Get All Kittens

VPAY authenticates your API requests using your account’s API keys. If you do not include your key when making an API request or use one that is incorrect or outdated, VPAY returns an error.

## Test Cards

When building with VPAY, we understand you need to test your implementations in a test environment before going live. That is why we've provided you with a list of test cards to use for test purposes. The cards cover a variety of use cases and simulations for failed and successful transactions with specific messages.

Test MasterCard PIN authentication
Card number: 5531 8866 5214 2950
cvv: 564
Expiry: 09/32
Pin: 3310
OTP: 12345

Test Visa Card 3D-Secure authentication (VBVSECURECODE)
Card number: 4187 4274 1556 4246
cvv: 828
Expiry: 09/32
Pin: 3310
OTP: 12345

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
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
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
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
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
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

