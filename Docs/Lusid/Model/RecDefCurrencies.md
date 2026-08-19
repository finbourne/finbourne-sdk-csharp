# Finbourne.Sdk.Lusid.Model.RecDefCurrencies

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Required | The currency used on the left side of the reconciliation. |
| **Right** | **string** | Required | The currency used on the right side of the reconciliation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefCurrencies(
    left: "...",  // required — The currency used on the left side of the reconciliation.
    right: "..."  // required — The currency used on the right side of the reconciliation.
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

