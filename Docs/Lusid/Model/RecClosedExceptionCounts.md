# Finbourne.Sdk.Lusid.Model.RecClosedExceptionCounts

Counts for results that are exceptions with a Closed status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Total** | **int** | Required | The total number of results in this category. |
| **ByClosureType** | [RecExceptionCountByClosureType](RecExceptionCountByClosureType.md) | Required | *No description available.* |
| **ByReviewStatus** | [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecClosedExceptionCounts(
    total: 0,  // required — The total number of results in this category.
    byClosureType: new RecExceptionCountByClosureType(...),  // required
    byReviewStatus: new RecResultCountByReviewStatus(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecClosedExceptionCounts>(json);
```

- [RecExceptionCountByClosureType](RecExceptionCountByClosureType.md)
- [RecResultCountByReviewStatus](RecResultCountByReviewStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

