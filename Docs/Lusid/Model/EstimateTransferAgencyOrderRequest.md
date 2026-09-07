# Finbourne.Sdk.Lusid.Model.EstimateTransferAgencyOrderRequest

A request to estimate the values of one order. `OrderId` is required whether or not the order has been  saved, because it is the identity the estimate is returned against. Supply `Order` to estimate values  that differ from - or do not yet exist in - the saved order.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Order** | [TransferAgencyOrderToEstimate](TransferAgencyOrderToEstimate.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateTransferAgencyOrderRequest(
    orderId: new ResourceId(...),  // required
    order: new TransferAgencyOrderToEstimate(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateTransferAgencyOrderRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TransferAgencyOrderToEstimate](TransferAgencyOrderToEstimate.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

