# Service Categories

## Get Service Categories
 
Get a list of available Service categories.

> Example request:

```shell
curl 'http://localhost:8080/serviceCategories'
```

```java
ServiceClient client = new ServiceClient("http://localhost");
ServiceCategories serviceCategories = client.getServiceCategories();
```

> Returned response:

```json
{
	"serviceCategories": ["Transfer", "Computation", "Storage", "DNS", "Internet of Things"]
}
```

### HTTP Request

`GET http://localhost:8080/serviceCategories`