# Finbourne.Sdk.Lusid.Model.RecommendedSortBy

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Required | The property key, identifier type, or field to be sorted by. |
| **SortOrder** | **string** | Optional | The sorting direction. Either ascending (ASC) or descending (DESC). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecommendedSortBy(
    attributeName: "...",  // required — The property key, identifier type, or field to be sorted by.
    sortOrder: "..."  // optional — The sorting direction. Either ascending (ASC) or descending (DESC).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecommendedSortBy>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

