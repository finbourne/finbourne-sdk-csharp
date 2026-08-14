# Finbourne.Sdk.Lusid.Model.RecResultAssignmentUpdate

An assignment update (assigned user or role) within a batch review item. Omitting the object leaves  the existing value untouched; a null value nullifies it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Optional | The value to set, or null to nullify. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultAssignmentUpdate(
    value: "..."  // optional — The value to set, or null to nullify.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultAssignmentUpdate>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

