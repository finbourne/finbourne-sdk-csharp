# Finbourne.Sdk.Lusid.Model.TransferAgencyOrderResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionId** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyOrderResult(
    orderId: new ResourceId(...),  // optional
    transactionId: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyOrderResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

