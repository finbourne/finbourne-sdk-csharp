# Finbourne.Sdk.Lusid.Model.CollateralAllocationOverride

An asset and the units of it a user chooses to move for a margin call, validated against the agreement's  constraints as the allocation is.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentId** | **string** | Required | The LUSID instrument identifier of the asset to move, or CCY_ and the currency code for cash. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Units** | **decimal** | Required | The units to move. |
| **CustodianAccount** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAllocationOverride(
    instrumentId: "...",  // required — The LUSID instrument identifier of the asset to move, or CCY_ and the currency code for cash.
    portfolioId: new ResourceId(...),  // required
    units: 0.0d,  // required — The units to move.
    custodianAccount: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAllocationOverride>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

