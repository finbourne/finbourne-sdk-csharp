# Finbourne.Sdk.Luminesce.Model.ExpressionWithAlias

Contract for an expression of data we \"have\" that we may \"want to map to a table-parameter's column\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Expression** | **string** | Required | Expression (column name, constant, complex expression, etc.) |
| **Alias** | **string** | Optional | Column Alias for the expression |
| **Flags** | **MappingFlags** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExpressionWithAlias(
    expression: "...",  // required — Expression (column name, constant, complex expression, etc.)
    alias: "...",  // optional — Column Alias for the expression
    flags:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExpressionWithAlias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

