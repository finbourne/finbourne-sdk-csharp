# Finbourne.Sdk.Lusid.Model.ReconciliationConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [ReconciliationSideConfiguration](ReconciliationSideConfiguration.md) | Optional | *No description available.* |
| **Right** | [ReconciliationSideConfiguration](ReconciliationSideConfiguration.md) | Optional | *No description available.* |
| **MappingId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationConfiguration(
    left: new ReconciliationSideConfiguration(...),  // optional
    right: new ReconciliationSideConfiguration(...),  // optional
    mappingId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationConfiguration>(json);
```


## Related Models

- [ReconciliationSideConfiguration](ReconciliationSideConfiguration.md)
- [ReconciliationSideConfiguration](ReconciliationSideConfiguration.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

