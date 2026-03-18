# Finbourne.Sdk.Identity.Model.NetworkZonesApplyRules

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SessionType** | **List&lt;string&gt;** | Required | *No description available.* |
| **UserRoles** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new NetworkZonesApplyRules(
    sessionType: ,  // required
    userRoles:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NetworkZonesApplyRules>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

