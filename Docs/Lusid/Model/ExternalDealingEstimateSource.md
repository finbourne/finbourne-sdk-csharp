# Finbourne.Sdk.Lusid.Model.ExternalDealingEstimateSource

The system that sent an external order set, and its own reference for the batch.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **System** | **string** | Required | *No description available.* |
| **Reference** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalDealingEstimateSource(
    varSystem: "...",  // required
    reference: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalDealingEstimateSource>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

