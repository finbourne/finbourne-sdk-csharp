# Finbourne.Sdk.Luminesce.Model.OnClauseTermDesign

A single on clause term (a pair of columns to join or a column to filter on)
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftTableField** | **string** | Optional | Name of field in the left table to join to (complex expressions are not supported at this time) |
| **RightTableField** | **string** | Optional | Name of field in the left table to join to (complex expressions are not supported at this time) |
| **Operator** | **QueryDesignerBinaryOperator** | Required | *No description available.* |
| **FilterValue** | **string** | Optional | The value to compare against (always as a string, but will be formatted to the correct type) |
| **FilterValueDataType** | **DataType** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OnClauseTermDesign(
    leftTableField: "...",  // optional — Name of field in the left table to join to (complex expressions are not supported at this time)
    rightTableField: "...",  // optional — Name of field in the left table to join to (complex expressions are not supported at this time)
    varOperator: ,  // required
    filterValue: "...",  // optional — The value to compare against (always as a string, but will be formatted to the correct type)
    filterValueDataType:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OnClauseTermDesign>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

