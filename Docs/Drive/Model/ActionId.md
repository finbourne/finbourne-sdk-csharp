# Finbourne.Sdk.Drive.Model.ActionId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Activity** | **string** | Required | *No description available.* |
| **Entity** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new ActionId(
    scope: "...",  // required
    activity: "...",  // required
    entity: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

