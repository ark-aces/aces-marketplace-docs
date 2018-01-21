# Services

## List Services
 
Gets a page of Services.

> Example request:

```shell
url="http://localhost:8080/services"
url="$url?category=Computation"
url="$url?search=ACES"
url="$url?pageSize=100"
url="$url&page=4"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ServicesListRequest request = new ServicesListRequest();
request.setCategory("Computation");
request.setSearch("ACES");
request.setPageSize(100);
request.setPage(1);


Page<Services> servicesPage = client.getServicesPage(request);
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

`GET http://localhost:8080/listener?pageSize=100&page=1&category=Computation&search=ACES`

## Get Service by id

Gets detailed information for a particular Service.

> Example request:

```shell
url="http://localhost:8080/services/{id}"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");
ServiceByIdRequest request = new ServiceByIdtRequest();
Page<ServiceById> ServiceByIdPage = client.getServiceByIdPage(request);
```

> Returned response:

```json
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
```

## Get Service Contracts by id

Get a page of Contracts created under the current Account.

> Example request:

```shell
url="http://localhost:8080/services/{id}/contracts"
url="$url?pageSize=100"
url="$url&page=4"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ServiceContractsRequest request = new ServiceContractsRequest();
request.setPageSize(100);
request.setPage(1);


Page<ServiceContracts> serviceContractsPage = client.getServiceContractsPage(request);
```
> Returned response:

```json
{
  "pageSize": "100",
  "page": "1",
  "totalItems: "1",
  "items": [
    {
      "id": "123",
      "serviceId": "abc",
      "status": "active",
      "results": "service outputSchema"
    }
  ]
}
```

## Create Service Contract.

Creates a new Service Contract under the current Account.