# Finbourne.Sdk.Lusid.Model.FeeTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the fee type. |
| **Description** | **string** | Optional | The description of the fee type. |
| **ComponentTransactions** | [List&lt;ComponentTransaction&gt;](ComponentTransaction.md) | Required | A set of component transactions that relate to the fee type to be created. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeTypeRequest(
    code: "...",  // required
    displayName: "...",  // required — The name of the fee type.
    description: "...",  // optional — The description of the fee type.
    componentTransactions: new List<ComponentTransaction>()  // required — A set of component transactions that relate to the fee type to be created.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeTypeRequest>(json);
```

- [ComponentTransaction](ComponentTransaction.md) — used in `ComponentTransactions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

