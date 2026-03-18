# Finbourne.Sdk.Horizon.Model.AllowedParameterValue

An allowed parameter value for an OpenFigi Parameter Option.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllowedValue** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AllowedParameterValue(
    allowedValue: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllowedParameterValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

