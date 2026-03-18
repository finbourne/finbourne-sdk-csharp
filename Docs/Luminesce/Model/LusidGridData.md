# Finbourne.Sdk.Luminesce.Model.LusidGridData

Representation of the data we will get from the dashboard
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidGridDesign** | [TableView](TableView.md) | Required | *No description available.* |
| **ResourceId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DashboardType** | **DashboardType** | Optional | *No description available.* |
| **UseSettleDate** | **bool?** | Optional | Whether to use the Settlement date or the Transaction date |
| **Dates** | [DateParameters](DateParameters.md) | Optional | *No description available.* |
| **Recipe** | **string** | Optional | The recipe to use for valuations |
| **Currency** | **string** | Optional | The currency to use for valuations |
| **Tenor** | **string** | Optional | The tenor to use for valuations |
| **OrderFlow** | **string** | Optional | Type of order flow to include |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new LusidGridData(
    lusidGridDesign: new TableView(...),  // required
    resourceId: new ResourceId(...),  // required
    dashboardType: ,  // optional
    useSettleDate: true,  // optional — Whether to use the Settlement date or the Transaction date
    dates: new DateParameters(...),  // optional
    recipe: "...",  // optional — The recipe to use for valuations
    currency: "...",  // optional — The currency to use for valuations
    tenor: "...",  // optional — The tenor to use for valuations
    orderFlow: "..."  // optional — Type of order flow to include
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidGridData>(json);
```


## Related Models

- [TableView](TableView.md)
- [ResourceId](ResourceId.md)
- [DateParameters](DateParameters.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

