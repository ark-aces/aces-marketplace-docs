# Listeners

## List Listeners
 
Gets a page of Listeners.

> Example request:

```shell
url="http://localhost:8080/listeners"
url="$url?pageSize=100"
url="$url&page=4"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ListenersRequest request = new ListenersRequest();
request.setCategory("BTC");
request.setSearch("ACES_Mainnet");
request.setPageSize(100);
request.setPage(1);


Page<Listeners> listenersPage = client.getListenersPage(request);
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

`GET http://localhost:8080/listener?pageSize=100&page=4&category=BTC&search=ACES_Mainnet`