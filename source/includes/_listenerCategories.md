# Listener Categories

## Get Listener Categories
 
Get a list of available Listener categories.

> Example request:

```shell
curl 'http://localhost:8080/listenerCategories'
```

```java
ServiceClient client = new ServiceClient("http://localhost");
ListenerCategories listenerCategories = client.getListenerCategories();
```

> Returned response:

```json
{
	"listenerCategories": ["BTC", "ETH", "ARK"]
}
```

### HTTP Request

`GET http://localhost:8080/listenerCategories`