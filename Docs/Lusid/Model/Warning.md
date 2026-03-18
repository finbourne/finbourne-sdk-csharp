# Finbourne.Sdk.Lusid.Model.Warning

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityId** | **string** | Required | *No description available.* |
| **Message** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Warning(
    entityId: "...",  // required
    message: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Warning>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

