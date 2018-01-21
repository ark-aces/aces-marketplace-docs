# Health

## Get Health
 
Get application health information.

> Example request:

```shell
curl 'http://localhost:8080/Health'
```

```java
ServiceClient client = new ServiceClient("http://localhost");
Health health = client.getHealth();
```

> Returned response:

```json
{
	"status": "up"
}
```

### HTTP Request

`GET http://localhost:8080/Health`