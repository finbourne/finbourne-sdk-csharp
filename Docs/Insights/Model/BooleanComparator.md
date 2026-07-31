# Finbourne.Sdk.Insights.Model.BooleanComparator

Filters a boolean field by comparing it to a supplied boolean value.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operation** | **string** | Required | The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.BooleanComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.BooleanOperation values (EqualTo, NotEqualTo); discoverable via the queryable-fields metadata endpoint. |
| **Value** | **bool** | Required | The value to compare the field against. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new BooleanComparator(
    operation: "...",  // required — The comparison to apply between the field and Finbourne.Insights.WebApi.Dtos.Querying.BooleanComparator.Value. One of the Finbourne.Insights.WebApi.Dtos.Querying.BooleanOperation values (EqualTo, NotEqualTo); discoverable via the queryable-fields metadata endpoint.
    value: true  // required — The value to compare the field against.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BooleanComparator>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

