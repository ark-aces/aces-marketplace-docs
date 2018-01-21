# Contracts

## Get Service Contracts.
 
Get a page of Contracts created under the current Account.

> Example request:

```shell
url="http://localhost:8080/contracts"
url="$url?name=serviceId"
url="$url?pageSize=100"
url="$url&page=1"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ContractsListRequest request = new ContractsListRequest();
request.setName("serviceId");
request.setPageSize(100);
request.setPage(1);


Page<Contracts> contractsPage = client.getContractsPage(request);
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

### HTTP Request

`GET http://localhost:8080/contracts?pageSize=100&page=1`

## Get Contract

Gets detailed information for a particular Contract.

> Example request:

```shell
url="http://localhost:8080/contracts/{id}"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ContractRequest request = new ContractRequest();

Page<Contract> contractPage = client.getContractPage(request);
```

> Returned response:

```json
{
      "id": "123",
      "serviceId": "abc",
      "status": "active",
      "results": "service outputSchema"
}
```

### HTTP Request

`GET http://localhost:8080/contracts/{id}`

## Cancel contract

Cancels a Contract.

> Example request:

```shell
url="http://localhost:8080/contracts/{id}/cancel"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ContractCancelRequest request = new ContractCancelRequest();

Page<ContractCancel> contractCancelPage = client.getContractCancelPage(request);
```
> Returned response:

```json
{
    "createdAt": "2017-11-01T00:00:00.000Z"
}
```

### HTTP Request

`GET http://localhost:8080/contracts/{id}/cancel`

## Create Ark Payment

Adds an Ark Payment for a Contract. The Contract must support the arkPayable interface.

> Example request:

```shell
url="http://localhost:8080/contracts/{id}/arkPayments"
url="$url?type=full"
url="$url?arkAmount=100"
curl -X GET "$url"  
```

```java
ServiceClient client = new ServiceClient("http://localhost");

ArkPayentRequest request = new ArkPaymentRequest();

Page<ArkPayment> arkPaymentPage = client.getArkPaymentPage(request);
```

> Returned response:

```json
{
    "amount": 100,
    "createdAt": "2017-11-01T00:00:00.000Z",
    "arkTransactionId": "adf021a947a15f3ffbef9a06926f87c5d4f164d54fc76a42d7bff4cb33081d89",
    "confirmations": 51
}
```

### HTTP Request

`GET http://localhost:8080/contracts/{id}/arkPayments?type=full&arkAmount=100`
