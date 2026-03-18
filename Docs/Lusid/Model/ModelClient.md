# Finbourne.Sdk.Lusid.Model.ModelClient

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ModelClient(
    name: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ModelClient>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

