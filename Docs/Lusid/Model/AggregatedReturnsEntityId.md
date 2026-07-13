# Finbourne.Sdk.Lusid.Model.AggregatedReturnsEntityId

Identifies an entity whose aggregated (time-weighted) returns are calculated: its scope, code and  type. Mirrors the valuation endpoint's entity identifier. Currently, supports only the  `Portfolio` entity type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Required | *No description available.* |
| **EntityType** | **string** | Required | Available values: Portfolio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturnsEntityId(
    scope: "...",  // required
    code: "...",  // required
    entityType: "..."  // required — Available values: Portfolio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedReturnsEntityId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

