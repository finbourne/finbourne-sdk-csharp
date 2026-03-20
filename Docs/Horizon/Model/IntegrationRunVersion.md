# Finbourne.Sdk.Horizon.Model.IntegrationRunVersion

Integration Run Version
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtCreated** | **DateTimeOffset?** | Optional | *No description available.* |
| **AsAtModified** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationRunVersion(
    asAtCreated: DateTimeOffset.Now,  // optional
    asAtModified: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationRunVersion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

