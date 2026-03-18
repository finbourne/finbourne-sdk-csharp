# Finbourne.Sdk.Lusid.Model.CustomSortBy

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The name of the field to sort by. |
| **PriorityValues** | **List&lt;string&gt;** | Optional | An optional list of priority field values to sort by, in the order they should be prioritized. |
| **RemainderOrder** | **string** | Required | The sorting direction for the remaining field values. Either ascending (ASC) or descending (DESC). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomSortBy(
    fieldName: "...",  // required — The name of the field to sort by.
    priorityValues: ,  // optional — An optional list of priority field values to sort by, in the order they should be prioritized.
    remainderOrder: "..."  // required — The sorting direction for the remaining field values. Either ascending (ASC) or descending (DESC).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomSortBy>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

