# Finbourne.Sdk.Access.Model.IfRequestHeaderExpression

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HeaderName** | **string** | Required | *No description available.* |
| **Operator** | **TextOperator** | Required | *No description available.* |
| **Value** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new IfRequestHeaderExpression(
    headerName: "...",  // required
    varOperator: ,  // required
    value: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IfRequestHeaderExpression>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

