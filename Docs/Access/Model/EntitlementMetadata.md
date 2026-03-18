# Finbourne.Sdk.Access.Model.EntitlementMetadata

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Provider** | **string** | Optional | *No description available.* |
| **Value** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new EntitlementMetadata(
    provider: "...",  // optional
    value: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EntitlementMetadata>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

