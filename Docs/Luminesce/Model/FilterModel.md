# Finbourne.Sdk.Luminesce.Model.FilterModel

Representation of the data used in a filter for the where clause
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FilterType** | **FilterType** | Required | *No description available.* |
| **Type** | **Type** | Optional | *No description available.* |
| **Filter** | **string** | Optional | The filter value |
| **FilterTo** | **decimal?** | Optional | The upper bound filter value for the number filter type |
| **Values** | **List&lt;string&gt;** | Optional | An array of possible values for the set filter type |
| **DateFrom** | **string** | Optional | A lower bound date for the date filter type |
| **DateTo** | **string** | Optional | An upper bound date for the date filter type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FilterModel(
    filterType: ,  // required
    type: ,  // optional
    filter: "...",  // optional — The filter value
    filterTo: 0.0d,  // optional — The upper bound filter value for the number filter type
    values: ,  // optional — An array of possible values for the set filter type
    dateFrom: "...",  // optional — A lower bound date for the date filter type
    dateTo: "..."  // optional — An upper bound date for the date filter type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FilterModel>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

