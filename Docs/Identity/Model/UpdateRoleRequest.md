# Finbourne.Sdk.Identity.Model.UpdateRoleRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | The description for this role |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdateRoleRequest(
    description: "..."  // optional — The description for this role
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRoleRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

