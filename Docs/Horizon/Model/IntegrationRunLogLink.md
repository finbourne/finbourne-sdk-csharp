# Finbourne.Sdk.Horizon.Model.IntegrationRunLogLink

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationRunLogLink(
    href: "...",  // required
    description: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationRunLogLink>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

