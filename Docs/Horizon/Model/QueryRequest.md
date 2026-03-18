# Finbourne.Sdk.Horizon.Model.QueryRequest

Used to control queries, including getting \"pages\" of data
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Specification** | [QuerySpecification](QuerySpecification.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new QueryRequest(
    specification: new QuerySpecification(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryRequest>(json);
```


## Related Models

- [QuerySpecification](QuerySpecification.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

