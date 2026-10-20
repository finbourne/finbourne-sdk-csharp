# Finbourne.Sdk.Lusid.Model.MarginLine

One holding's contribution to a margin call: its exposure, or its value as collateral.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run that produced the line. |
| **AgreementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Item** | **string** | Required | The margin item the line falls under. Filterable. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **HoldingId** | **string** | Optional | The holding the line was valued from. |
| **CustodianAccountScope** | **string** | Optional | The scope of the custodian account the holding sits in, when it has one. |
| **CustodianAccountCode** | **string** | Optional | The code of the custodian account the holding sits in, when it has one. |
| **CustodianAccountName** | **string** | Optional | The name of the custodian account, when it has one. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The identifiers of the instrument held. |
| **Units** | **decimal** | Required | The units held. |
| **Pv** | **decimal?** | Optional | The present value of the holding in the agreement&#39;s base currency, when it contributes to exposure. |
| **VariationMargin** | **decimal?** | Optional | The holding&#39;s contribution to variation margin, when it contributes to exposure. |
| **CollateralValue** | **decimal?** | Optional | The holding&#39;s value as collateral after haircuts, when it is held as collateral. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginLine(
    runId: "...",  // required — The run that produced the line.
    agreementId: new ResourceId(...),  // required
    item: "...",  // required — The margin item the line falls under. Filterable.
    portfolioId: new ResourceId(...),  // optional
    holdingId: "...",  // optional — The holding the line was valued from.
    custodianAccountScope: "...",  // optional — The scope of the custodian account the holding sits in, when it has one.
    custodianAccountCode: "...",  // optional — The code of the custodian account the holding sits in, when it has one.
    custodianAccountName: "...",  // optional — The name of the custodian account, when it has one.
    instrumentIdentifiers: ,  // required — The identifiers of the instrument held.
    units: 0.0d,  // required — The units held.
    pv: 0.0d,  // optional — The present value of the holding in the agreement&#39;s base currency, when it contributes to exposure.
    variationMargin: 0.0d,  // optional — The holding&#39;s contribution to variation margin, when it contributes to exposure.
    collateralValue: 0.0d  // optional — The holding&#39;s value as collateral after haircuts, when it is held as collateral.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginLine>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

