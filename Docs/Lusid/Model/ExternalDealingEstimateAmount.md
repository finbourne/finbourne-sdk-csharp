# Finbourne.Sdk.Lusid.Model.ExternalDealingEstimateAmount

A cash amount in a stated currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **decimal** | Required | *No description available.* |
| **Currency** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalDealingEstimateAmount(
    value: 0.0d,  // required
    currency: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalDealingEstimateAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

