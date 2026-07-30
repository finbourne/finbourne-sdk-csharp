# Finbourne.Sdk.Lusid.Model.RecMatchCounts

Counts for non-exception results (Match, Cross).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Total** | **int** | Required | The total number of results in this category. |
| **ByResultType** | [RecMatchCountByResultType](RecMatchCountByResultType.md) | Required | *No description available.* |
| **ByReviewStatus** | [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecMatchCounts(
    total: 0,  // required — The total number of results in this category.
    byResultType: new RecMatchCountByResultType(...),  // required
    byReviewStatus: new RecResultCountByReviewStatus(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecMatchCounts>(json);
```

- [RecMatchCountByResultType](RecMatchCountByResultType.md)
- [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

