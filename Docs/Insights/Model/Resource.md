# Finbourne.Sdk.Insights.Model.Resource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | *No description available.* |
| **Identifier** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new Resource(
    type: "...",  // optional
    identifier: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Resource>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

