# Finbourne.Sdk.Lusid.Model.FeeSizeTier

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LowerBound** | **decimal** | Required | *No description available.* |
| **UpperBound** | **decimal?** | Optional | *No description available.* |
| **Rate** | **decimal** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeSizeTier(
    lowerBound: 0.0d,  // required
    upperBound: 0.0d,  // optional
    rate: 0.0d  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeSizeTier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

