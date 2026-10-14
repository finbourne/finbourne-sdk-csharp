# Finbourne.Sdk.Lusid.Model.UpsertTransferAgencyTransactionFromOrderRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PriceDate** | **DateTimeOffset** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertTransferAgencyTransactionFromOrderRequest(
    orderId: new ResourceId(...),  // required
    priceDate: DateTimeOffset.Now  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertTransferAgencyTransactionFromOrderRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

