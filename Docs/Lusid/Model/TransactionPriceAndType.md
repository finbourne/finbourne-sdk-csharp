# Finbourne.Sdk.Lusid.Model.TransactionPriceAndType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Price** | **string** | Optional | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionPriceAndType(
    price: "...",  // optional
    type: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionPriceAndType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

