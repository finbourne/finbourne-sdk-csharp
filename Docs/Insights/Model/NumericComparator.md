# Finbourne.Sdk.Insights.Model.NumericComparator

Filters a numeric field by comparing it to a supplied numeric value.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operation** | **string** | Required | The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.NumericComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.NumericOperation values (e.g. EqualTo, GreaterThan); discoverable via the queryable-fields metadata endpoint. |
| **Value** | **decimal** | Required | The value to compare the field against. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new NumericComparator(
    operation: "...",  // required — The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.NumericComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.NumericOperation values (e.g. EqualTo, GreaterThan); discoverable via the queryable-fields metadata endpoint.
    value: 0.0d  // required — The value to compare the field against.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NumericComparator>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

