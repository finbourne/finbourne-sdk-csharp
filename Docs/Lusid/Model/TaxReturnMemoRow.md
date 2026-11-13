# Finbourne.Sdk.Lusid.Model.TaxReturnMemoRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Optional | The label of the period, for example the four-digit year. |
| **Amount** | **decimal** | Optional | The amount, in pounds. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnMemoRow(
    label: "...",  // optional — The label of the period, for example the four-digit year.
    amount: 0.0d  // optional — The amount, in pounds.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnMemoRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

