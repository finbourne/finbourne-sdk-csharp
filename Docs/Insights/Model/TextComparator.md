# Finbourne.Sdk.Insights.Model.TextComparator

Filters a text field. Single-value operations (EqualTo, NotEqualTo, StartsWith, EndsWith) compare the field to Finbourne.Insights.WebApi.Dtos.Querying.TextComparator.Value; set operations (In, NotIn) compare it to Finbourne.Insights.WebApi.Dtos.Querying.TextComparator.Values. Exactly one of Finbourne.Insights.WebApi.Dtos.Querying.TextComparator.Value or Finbourne.Insights.WebApi.Dtos.Querying.TextComparator.Values is supplied, matching the chosen Finbourne.Insights.WebApi.Dtos.Querying.TextComparator.Operation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operation** | **string** | Required | The comparison to apply between the field and the supplied value(s). One of the Finbourne.Insights.WebApi.Dtos.Querying.TextOperation values (e.g. EqualTo, StartsWith, In); discoverable via the queryable-fields metadata endpoint. |
| **Value** | **string** | Optional | The value to compare the field against, for the single-value operations (EqualTo, NotEqualTo, StartsWith, EndsWith). |
| **Values** | **List&lt;string&gt;** | Optional | The set of values to compare the field against, for the set operations (In, NotIn). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TextComparator(
    operation: "...",  // required — The comparison to apply between the field and the supplied value(s). One of the Finbourne.Insights.WebApi.Dtos.Querying.TextOperation values (e.g. EqualTo, StartsWith, In); discoverable via the queryable-fields metadata endpoint.
    value: "...",  // optional — The value to compare the field against, for the single-value operations (EqualTo, NotEqualTo, StartsWith, EndsWith).
    values:   // optional — The set of values to compare the field against, for the set operations (In, NotIn).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TextComparator>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

