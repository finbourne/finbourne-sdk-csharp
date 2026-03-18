# Finbourne.Sdk.Configuration.Model.UpdateConfigurationSet

The information required to update a configuration set
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | The new description of the configuration set |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new UpdateConfigurationSet(
    description: "..."  // optional — The new description of the configuration set
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateConfigurationSet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

