# Finbourne.Sdk.Luminesce.Model.ColumnStateType

Representation of a column within the grid
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColId** | **string** | Required | Unique identifier for the column |
| **Hide** | **bool** | Required | Flag to determine whether the column is visible in the grid |
| **Sort** | **string** | Optional | The sort order (asc or desc) |
| **SortIndex** | **int?** | Optional | The index of the sort to determine the order in which the sorts are applied |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ColumnStateType(
    colId: "...",  // required — Unique identifier for the column
    hide: true,  // required — Flag to determine whether the column is visible in the grid
    sort: "...",  // optional — The sort order (asc or desc)
    sortIndex: 0  // optional — The index of the sort to determine the order in which the sorts are applied
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ColumnStateType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

