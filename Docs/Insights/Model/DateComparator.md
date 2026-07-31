# Finbourne.Sdk.Insights.Model.DateComparator

Filters a date/time field by comparing it to a supplied date/time value.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operation** | **string** | Required | The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.DateComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.DateOperation values (e.g. Before, OnOrAfter); discoverable via the queryable-fields metadata endpoint. |
| **Value** | **DateTimeOffset** | Required | The value to compare the field against. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new DateComparator(
    operation: "...",  // required — The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.DateComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.DateOperation values (e.g. Before, OnOrAfter); discoverable via the queryable-fields metadata endpoint.
    value: DateTimeOffset.Now  // required — The value to compare the field against.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateComparator>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

