# Finbourne.Sdk.Lusid.Model.PropertyFilter

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Optional | The key that uniquely identifies a queryable address in Lusid. |
| **Operator** | **string** | Optional | The available values are: Equals, NotEquals, GreaterThan, GreaterThanOrEqualTo, LessThan, LessThanOrEqualTo, In, StartsWith |
| **Right** | **Object** | Optional | *No description available.* |
| **RightOperandType** | **string** | Optional | The available values are: Absolute, Property |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyFilter(
    left: "...",  // optional — The key that uniquely identifies a queryable address in Lusid.
    varOperator: "...",  // optional — The available values are: Equals, NotEquals, GreaterThan, GreaterThanOrEqualTo, LessThan, LessThanOrEqualTo, In, StartsWith
    right: ,  // optional
    rightOperandType: "..."  // optional — The available values are: Absolute, Property
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyFilter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

