# Finbourne.Sdk.Luminesce.Model.BackgroundQueryProgressResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HasData** | **bool** | Optional | Is there currently data for this Query? |
| **RowCount** | **int** | Optional | Number of rows of data held. -1 if none as yet. |
| **Status** | **TaskStatus** | Optional | *No description available.* |
| **State** | **BackgroundQueryState** | Optional | *No description available.* |
| **Progress** | **string** | Optional | The full progress log (up to this point at least) |
| **Feedback** | [List&lt;FeedbackEventArgs&gt;](FeedbackEventArgs.md) | Optional | Individual Feedback Messages (to replace Progress).  A given message will be returned from only one call. |
| **Query** | **string** | Optional | The LuminesceSql of the original request |
| **QueryName** | **string** | Optional | The QueryName given in the original request |
| **ColumnsAvailable** | [List&lt;Column&gt;](Column.md) | Optional | When HasData is true this is the schema of columns that will be returned if the data is requested |
| **Lineage** | [TableLineage](TableLineage.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundQueryProgressResponse(
    hasData: true,  // optional — Is there currently data for this Query?
    rowCount: 0,  // optional — Number of rows of data held. -1 if none as yet.
    status: ,  // optional
    state: ,  // optional
    progress: "...",  // optional — The full progress log (up to this point at least)
    feedback: new List<FeedbackEventArgs>(),  // optional — Individual Feedback Messages (to replace Progress).  A given message will be returned from only one call.
    query: "...",  // optional — The LuminesceSql of the original request
    queryName: "...",  // optional — The QueryName given in the original request
    columnsAvailable: new List<Column>(),  // optional — When HasData is true this is the schema of columns that will be returned if the data is requested
    lineage: new TableLineage(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundQueryProgressResponse>(json);
```

- [FeedbackEventArgs](FeedbackEventArgs.md) — used in `Feedback`
- [Column](Column.md) — used in `ColumnsAvailable`
- [TableLineage](TableLineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

