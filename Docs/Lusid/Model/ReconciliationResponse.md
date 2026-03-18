# Finbourne.Sdk.Lusid.Model.ReconciliationResponse

Class representing the set of comparisons that result from comparing holdings and their valuations between two separate evaluations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Comparisons** | [List&lt;ReconciliationLine&gt;](ReconciliationLine.md) | Optional | List of comparisons of left to right hand sides. |
| **DataSchema** | [ResultDataSchema](ResultDataSchema.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationResponse(
    comparisons: new List<ReconciliationLine>(),  // optional — List of comparisons of left to right hand sides.
    dataSchema: new ResultDataSchema(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationResponse>(json);
```


## Related Models

- [ReconciliationLine](ReconciliationLine.md) — used in `Comparisons`
- [ResultDataSchema](ResultDataSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

