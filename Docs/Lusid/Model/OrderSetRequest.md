# Finbourne.Sdk.Lusid.Model.OrderSetRequest

A request to create or update multiple Orders.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderRequests** | [List&lt;OrderRequest&gt;](OrderRequest.md) | Optional | A collection of OrderRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderSetRequest(
    orderRequests: new List<OrderRequest>()  // optional — A collection of OrderRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderSetRequest>(json);
```


## Related Models

- [OrderRequest](OrderRequest.md) — used in `OrderRequests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

