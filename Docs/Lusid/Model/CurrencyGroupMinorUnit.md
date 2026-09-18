# Finbourne.Sdk.Lusid.Model.CurrencyGroupMinorUnit

A minor unit currency within a currency group.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Required | The three to five letter, case-sensitive currency code of the minor unit, e.g. GBX. |
| **FractionOfMajor** | **decimal** | Required | The fraction of the major unit that one minor unit is worth, greater than zero and no more than one, e.g. 0.01 for GBX against GBP. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CurrencyGroupMinorUnit(
    currency: "...",  // required — The three to five letter, case-sensitive currency code of the minor unit, e.g. GBX.
    fractionOfMajor: 0.0d  // required — The fraction of the major unit that one minor unit is worth, greater than zero and no more than one, e.g. 0.01 for GBX against GBP.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CurrencyGroupMinorUnit>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

