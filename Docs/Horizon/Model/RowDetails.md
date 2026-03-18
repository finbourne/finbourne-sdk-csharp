# Finbourne.Sdk.Horizon.Model.RowDetails

Information about the nuber of rows processed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RowsTotal** | **int?** | Optional | The number of rows processed. |
| **RowsSucceeded** | **int?** | Optional | The number of rows that were successfully processed. |
| **RowsIgnored** | **int?** | Optional | The number of rows that were not processed. |
| **RowsFailed** | **int?** | Optional | The number of rows that failed when being processed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new RowDetails(
    rowsTotal: 0,  // optional — The number of rows processed.
    rowsSucceeded: 0,  // optional — The number of rows that were successfully processed.
    rowsIgnored: 0,  // optional — The number of rows that were not processed.
    rowsFailed: 0  // optional — The number of rows that failed when being processed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RowDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

