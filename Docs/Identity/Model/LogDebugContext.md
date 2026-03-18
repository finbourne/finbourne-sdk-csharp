# Finbourne.Sdk.Identity.Model.LogDebugContext

Represents a LogDebugContext resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DebugData** | **Dictionary&lt;string, Object&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogDebugContext(
    debugData:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogDebugContext>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

