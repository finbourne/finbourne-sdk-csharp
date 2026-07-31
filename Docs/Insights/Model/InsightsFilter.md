# Finbourne.Sdk.Insights.Model.InsightsFilter

A single filter applied to a queryable log field. Exactly one comparator (Finbourne.Insights.WebApi.Dtos.Querying.InsightsFilter.Text, Finbourne.Insights.WebApi.Dtos.Querying.InsightsFilter.Numeric, Finbourne.Insights.WebApi.Dtos.Querying.InsightsFilter.Date or Finbourne.Insights.WebApi.Dtos.Querying.InsightsFilter.Boolean) must be populated, and its type must match the data type of the field named by Finbourne.Insights.WebApi.Dtos.Querying.InsightsFilter.Field. The available comparator and operation for a field can be discovered via the queryable-fields metadata endpoint.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Field** | **string** | Required | The name of the field to filter on (case-insensitive). Must be a filterable field of the queried log type. |
| **Text** | [TextComparator](TextComparator.md) | Optional | *No description available.* |
| **Numeric** | [NumericComparator](NumericComparator.md) | Optional | *No description available.* |
| **Date** | [DateComparator](DateComparator.md) | Optional | *No description available.* |
| **Boolean** | [BooleanComparator](BooleanComparator.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new InsightsFilter(
    field: "...",  // required — The name of the field to filter on (case-insensitive). Must be a filterable field of the queried log type.
    text: new TextComparator(...),  // optional
    numeric: new NumericComparator(...),  // optional
    date: new DateComparator(...),  // optional
    boolean: new BooleanComparator(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InsightsFilter>(json);
```

- [TextComparator](TextComparator.md)
- [NumericComparator](NumericComparator.md)
- [DateComparator](DateComparator.md)
- [BooleanComparator](BooleanComparator.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

