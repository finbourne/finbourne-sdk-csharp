# Finbourne.Sdk.Lusid.Model.RecDefCurrencies

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Optional | The currency used on the left side of the reconciliation. Required when the left side has portfolio sources; must be null when it draws on relational data. |
| **Right** | **string** | Optional | The currency used on the right side of the reconciliation. Required when the right side has portfolio sources; must be null when it draws on relational data. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefCurrencies(
    left: "...",  // optional — The currency used on the left side of the reconciliation. Required when the left side has portfolio sources; must be null when it draws on relational data.
    right: "..."  // optional — The currency used on the right side of the reconciliation. Required when the right side has portfolio sources; must be null when it draws on relational data.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefCurrencies>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

