# Finbourne.Sdk.Lusid.Model.UnitisationData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SharesInIssue** | **decimal** | Required | The number of shares in issue at a valuation point. |
| **UnitPrice** | **decimal** | Required | The price of one unit of the share class at a valuation point. |
| **NetDealingUnits** | **decimal** | Required | The net dealing in units for the share class at a valuation point. This could be the sum of negative redemptions (in units) and positive subscriptions (in units). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnitisationData(
    sharesInIssue: 0.0d,  // required — The number of shares in issue at a valuation point.
    unitPrice: 0.0d,  // required — The price of one unit of the share class at a valuation point.
    netDealingUnits: 0.0d  // required — The net dealing in units for the share class at a valuation point. This could be the sum of negative redemptions (in units) and positive subscriptions (in units).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnitisationData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

