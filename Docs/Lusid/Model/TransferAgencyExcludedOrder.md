# Finbourne.Sdk.Lusid.Model.TransferAgencyExcludedOrder

An order left out of the sizing an estimate was struck from, with the reason it was left out.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Reason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyExcludedOrder(
    orderId: new ResourceId(...),  // optional
    reason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyExcludedOrder>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

