# Finbourne.Sdk.Configuration.Model.CreateConfigurationSet

The information required to create a new configuration set
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | The type (personal or shared) of the new configuration set |
| **Description** | **string** | Optional | The description of the new configuration set |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new CreateConfigurationSet(
    id: new ResourceId(...),  // required
    type: "...",  // required — The type (personal or shared) of the new configuration set
    description: "..."  // optional — The description of the new configuration set
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateConfigurationSet>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

