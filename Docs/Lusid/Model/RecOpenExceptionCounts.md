# Finbourne.Sdk.Lusid.Model.RecOpenExceptionCounts

Counts for results that are exceptions with an Open status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Total** | **int** | Required | The total number of results in this category. |
| **ByResultType** | [RecExceptionCountByResultType](RecExceptionCountByResultType.md) | Required | *No description available.* |
| **ByReviewStatus** | [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecOpenExceptionCounts(
    total: 0,  // required — The total number of results in this category.
    byResultType: new RecExceptionCountByResultType(...),  // required
    byReviewStatus: new RecResultCountByReviewStatus(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecOpenExceptionCounts>(json);
```

- [RecExceptionCountByResultType](RecExceptionCountByResultType.md)
- [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

