# Finbourne.Sdk.Lusid.Model.TransferAgencyTransactionFromOrderResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **SecurityTransactionId** | **string** | Optional | *No description available.* |
| **AmendedCashTransactionId** | **string** | Optional | *No description available.* |
| **Price** | **decimal** | Optional | *No description available.* |
| **Units** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyTransactionFromOrderResult(
    orderId: new ResourceId(...),  // optional
    securityTransactionId: "...",  // optional
    amendedCashTransactionId: "...",  // optional
    price: 0.0d,  // optional
    units: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyTransactionFromOrderResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

