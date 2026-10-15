# Finbourne.Sdk.Lusid.Model.FeeRateTier

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rate** | **decimal** | Required | *No description available.* |
| **Threshold** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeRateTier(
    rate: 0.0d,  // required
    threshold: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeRateTier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

