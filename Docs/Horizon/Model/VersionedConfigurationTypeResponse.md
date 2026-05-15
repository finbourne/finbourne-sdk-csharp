# Finbourne.Sdk.Horizon.Model.VersionedConfigurationTypeResponse

Represents a registered versioned configuration type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConfigType** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new VersionedConfigurationTypeResponse(
    configType: "...",  // required
    displayName: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionedConfigurationTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

