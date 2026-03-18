# Finbourne.Sdk.Luminesce.Model.TableView

Representation of the table structure
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HeaderNames** | **Dictionary&lt;string, string&gt;** | Required | Mapping of column ids to aliases |
| **ColumnState** | [List&lt;ColumnStateType&gt;](ColumnStateType.md) | Required | Array of all columns in the dashboard |
| **Filters** | [Dictionary&lt;string, FilterModel&gt;](FilterModel.md) | Optional | Filters applied to columns in the dashboard |
| **Meta** | [TableMeta](TableMeta.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new TableView(
    headerNames: ,  // required — Mapping of column ids to aliases
    columnState: new List<ColumnStateType>(),  // required — Array of all columns in the dashboard
    filters: new FilterModel(...),  // optional — Filters applied to columns in the dashboard
    meta: new TableMeta(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TableView>(json);
```

- [ColumnStateType](ColumnStateType.md) — used in `ColumnState`
- [FilterModel](FilterModel.md) — used in `Filters`
- [TableMeta](TableMeta.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

