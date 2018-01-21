# Account

## List Account Users
 
Gets a page of Users registered under the current Account.

> Example request:

```shell
url="http://localhost:8080/account/user"
url="$url?pageSize=100"
url="$url&page=1"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

AccountUsersRequest request = new AccountUsersRequest();
request.setPageSize(100);
request.setPage(1);


Page<AccountUsers> accountUsersPage = client.getAccountUsersPage(request);
```

> Returned response:

```json
{
  "pageSize": "100",
  "page": "1",
  "totalItems: "1",
  "items": [
    {
      "id": "1",
      "name": "ACES BTC Mainnet Listener",
      "emailAddress": "joe@example.com",
      "status": "active",
      "createdAt": "2017-11-01T00:00:00.000Z"
    }
  ]
}
```

### HTTP Request

`GET http://localhost:8080/account/user`

## Get Ark Wallet

Get Ark Wallet attached to the current Account.

> Example request:

```shell
url="http://localhost:8080/account/arkWallet"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

AccountWalletRequest request = new AccountWalletRequest();

Page<AccountWallet> accountWalletPage = client.getAccountWalletPage(request);
```

> Returned response:

```json
{
  "address": "ARVpfb7dcyXefUFhfs8wP5v78yM9AokGi6",
  "balance": 42,
  "createdAt": "2017-11-01T00:00:00.000Z"
}
```

### HTTP Request

`GET http://localhost:8080/account/arkWallet`

## List Account Ark Wallet Transactions

Gets a page of Ark Wallet transactions for the current Account.

> Example request:

```shell
url="http://localhost:8080/account/arkWallet/transactions"
url="$url?pageSize=100"
url="$url&page=1"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

AccountWalletRequest request = new AccountWalletRequest();

Page<AccountWallet> accountWalletPage = client.getAccountWalletPage(request);
```

> Returned response:

```json
{
  "pageSize": "100",
  "page": "1",
  "totalItems: "1",
  "items": [
    {
      "amount": "42",
      "createdAt": "2017-11-01T00:00:00.000Z",
      "arkTransactionId": "adf021a947a15f3ffbef9a06926f87c5d4f164d54fc76a42d7bff4cb33081d89",
      "confirmations":"51"
    }
  ]
}
```

### HTTP Request

`GET http://localhost:8080/account/arkWallet/transactions`

## List Account Listeners

Gets a page of Listener registered under the current Account.

> Example request:

```shell
url="http://localhost:8080/account/listeners"
url="$url?category=BTC"
url="$url?search=ACES"
url="$url?pageSize=100"
url="$url&page=1"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

AccountListenersRequest request = new AccountListenersRequest();

Page<AccountListeners> accountListenerspage = client.getAccountListenersPage(request);
```

> Returned response:

```json
{
  "pageSize": "100",
  "page": "1",
  "totalItems: "1",
  "items": [
    {
      "id": "1",
      "url": "https://btc-listener-mainnet.arkaces.com",
      "name": "ACES BTC Mainnet Listener",
      "websiteUrl": "https://arkaces.com",
      "description": "A blockchain listener for BTC Mainnet",
      "authorizationType": "httpBasic",
      "minArkStake": "100",
      "dailyArkFee": "0",
      "createdAt": "2017-11-01T00:00:00.000Z"
    }
  ]
}
```

### HTTP Request

`GET http://localhost:8080/account/listeners`

## Create Listener

Creates a Listener registered under the current Account.


## List Account Services

Gets a page of Services registered under the current Account.

> Example request:

```shell
url="http://localhost:8080/account/services"
url="$url?category=BTC"
url="$url?search=ACES"
url="$url?pageSize=100"
url="$url&page=1"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

AccountListenersRequest request = new AccountListenersRequest();

Page<AccountListeners> accountListenerspage = client.getAccountListenersPage(request);
```

> Returned response:

```json
{
  "pageSize": "100",
  "page": "1",
  "totalItems: "1",
  "items": [
       {
          "id": "1",
          "url": "https://services.arkaces.com/computation",
          "name": "ACES Computation Services",
          "version": "1.0",
          "description": "A blockchain listener for BTC Mainnet",
          "instructions": "Usage instructions in basic html format.",
          "websiteUrl": "https://arkaces.com",
          "type":"onDemand",
          "inputSchema":"Contract input schema in JSON Schema format.",
          "outputSchema":"Contract output schema in JSON Schema format.",
          "createdAt": "2017-11-01T00:00:00.000Z"
        }
  ]
}
```

### HTTP Request

`GET http://localhost:8080/account/services`

## Create Account Service

Register a new Service under an Account.