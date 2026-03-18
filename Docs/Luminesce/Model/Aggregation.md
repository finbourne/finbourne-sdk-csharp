# Finbourne.Sdk.Luminesce.Model.Aggregation

How to aggregate over a field
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **AggregateFunction** | Required | *No description available.* |
| **Alias** | **string** | Optional | Alias, if any, for the Aggregate expression when selected |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new Aggregation(
    type: ,  // required
    alias: "..."  // optional — Alias, if any, for the Aggregate expression when selected
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Aggregation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

