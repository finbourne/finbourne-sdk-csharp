# Finbourne.Sdk.Insights.Model.QueryableLogField

Describes a field of a log type that can be selected and (where Finbourne.Insights.WebApi.Dtos.Querying.QueryableLogField.Filterable is set) filtered when querying logs, including the comparator operations available for it. Returned by the queryable-fields metadata endpoint so a UI can advertise the correct comparators for each field.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the field, as used when requesting it or filtering on it (case-insensitive). |
| **DataType** | **string** | Required | The data type of the field: Text, Numeric, Date or Boolean. |
| **SupportedOperations** | **List&lt;string&gt;** | Required | The comparator operations available for this field. Empty when the field is not filterable. |
| **Filterable** | **bool** | Optional | Whether the field can be used in a filter. |
| **AlwaysReturned** | **bool** | Optional | Whether the field is always returned (and therefore need not be requested). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new QueryableLogField(
    name: "...",  // required — The name of the field, as used when requesting it or filtering on it (case-insensitive).
    dataType: "...",  // required — The data type of the field: Text, Numeric, Date or Boolean.
    supportedOperations: ,  // required — The comparator operations available for this field. Empty when the field is not filterable.
    filterable: true,  // optional — Whether the field can be used in a filter.
    alwaysReturned: true  // optional — Whether the field is always returned (and therefore need not be requested).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryableLogField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

