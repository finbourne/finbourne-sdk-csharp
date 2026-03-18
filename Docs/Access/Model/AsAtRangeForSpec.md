# Finbourne.Sdk.Access.Model.AsAtRangeForSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | [AsAtPredicateContract](AsAtPredicateContract.md) | Required | *No description available.* |
| **To** | [AsAtPredicateContract](AsAtPredicateContract.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AsAtRangeForSpec(
    from: new AsAtPredicateContract(...),  // required
    to: new AsAtPredicateContract(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AsAtRangeForSpec>(json);
```


## Related Models

- [AsAtPredicateContract](AsAtPredicateContract.md)
- [AsAtPredicateContract](AsAtPredicateContract.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

