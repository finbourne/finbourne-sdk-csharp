# Finbourne.Sdk.Lusid.Model.DataScope

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarClient** | [ModelClient](ModelClient.md) | Optional | *No description available.* |
| **Scope** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataScope(
    varClient: new ModelClient(...),  // optional
    scope: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataScope>(json);
```


## Related Models

- [ModelClient](ModelClient.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

