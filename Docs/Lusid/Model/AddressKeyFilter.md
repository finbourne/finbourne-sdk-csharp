# Finbourne.Sdk.Lusid.Model.AddressKeyFilter

Class specifying a filtering operation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Optional | Address for the value in the row |
| **Operator** | **string** | Optional | What sort of comparison is the filter performing. Can be either \&quot;eq\&quot; for equals or \&quot;neq\&quot; for not equals. |
| **Right** | [ResultValue](ResultValue.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddressKeyFilter(
    left: "...",  // optional — Address for the value in the row
    varOperator: "...",  // optional — What sort of comparison is the filter performing. Can be either \&quot;eq\&quot; for equals or \&quot;neq\&quot; for not equals.
    right: new ResultValue(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddressKeyFilter>(json);
```

- [ResultValue](ResultValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

