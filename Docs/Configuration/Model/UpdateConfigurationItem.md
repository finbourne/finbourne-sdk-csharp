# Finbourne.Sdk.Configuration.Model.UpdateConfigurationItem

The information required to update a configuration item
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The new value of the configuration item |
| **Description** | **string** | Optional | The new description of the configuration item |
| **BlockReveal** | **bool** | Optional | The requested new state of BlockReveal |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new UpdateConfigurationItem(
    value: "...",  // required — The new value of the configuration item
    description: "...",  // optional — The new description of the configuration item
    blockReveal: true  // optional — The requested new state of BlockReveal
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateConfigurationItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

