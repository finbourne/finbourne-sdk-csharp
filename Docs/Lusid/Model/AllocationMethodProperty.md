# Finbourne.Sdk.Lusid.Model.AllocationMethodProperty

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code identifying the allocation method property. |
| **Scope** | **string** | Required | The scope of the allocation method property. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMethodProperty(
    code: "...",  // required — The code identifying the allocation method property.
    scope: "..."  // required — The scope of the allocation method property.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMethodProperty>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

