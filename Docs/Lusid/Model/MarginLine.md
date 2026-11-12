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
| **InitialMarginItem** | **string** | Optional | The initial-margin item the line falls under, when the holding matched one. Filterable. |
| **InitialMargin** | **decimal?** | Optional | The holding&#39;s share of its netting set&#39;s initial margin, before the threshold, when it contributes to it. |
| **Scenario** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **LineKey** | **string** | Optional | A key that identifies the line within its run, with which its explanation is asked for. A line valued under a scenario has a different key from the same holding in the base market. Null for a line stored before lines carried a key. |
| **ExplainAvailable** | **bool** | Optional | Whether the working behind the line&#39;s figures was stored, so that the line can be explained. One flag covers every figure of the line. |
| **InstrumentType** | **string** | Optional | LUSID&#39;s type for the instrument held, when the run read it. |
| **AssetClass** | **string** | Optional | The instrument&#39;s asset class, when the run read it. |
| **Currency** | **string** | Optional | The currency the holding is denominated in, when the run read it. |
| **MaturityDate** | **DateTimeOffset?** | Optional | The instrument&#39;s maturity, when it has one. |
| **Notional** | **decimal?** | Optional | The holding&#39;s notional in its own currency, when the instrument has one. |
| **GrossInitialMargin** | **decimal?** | Optional | The regulatory-grid charge on the holding before its netting set&#39;s net-to-gross scaling. Null under other methods. |
| **MovableTo** | **List&lt;string&gt;** | Required | The initial-margin netting sets of other agreements in the run the holding could be re-booked into, as scope/code/item. Recorded for base-case trading lines under an initial-margin item; empty otherwise. |


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
    collateralValue: 0.0d,  // optional — The holding&#39;s value as collateral after haircuts, when it is held as collateral.
    initialMarginItem: "...",  // optional — The initial-margin item the line falls under, when the holding matched one. Filterable.
    initialMargin: 0.0d,  // optional — The holding&#39;s share of its netting set&#39;s initial margin, before the threshold, when it contributes to it.
    scenario: new ResourceId(...),  // optional
    lineKey: "...",  // optional — A key that identifies the line within its run, with which its explanation is asked for. A line valued under a scenario has a different key from the same holding in the base market. Null for a line stored before lines carried a key.
    explainAvailable: true,  // optional — Whether the working behind the line&#39;s figures was stored, so that the line can be explained. One flag covers every figure of the line.
    instrumentType: "...",  // optional — LUSID&#39;s type for the instrument held, when the run read it.
    assetClass: "...",  // optional — The instrument&#39;s asset class, when the run read it.
    currency: "...",  // optional — The currency the holding is denominated in, when the run read it.
    maturityDate: DateTimeOffset.Now,  // optional — The instrument&#39;s maturity, when it has one.
    notional: 0.0d,  // optional — The holding&#39;s notional in its own currency, when the instrument has one.
    grossInitialMargin: 0.0d,  // optional — The regulatory-grid charge on the holding before its netting set&#39;s net-to-gross scaling. Null under other methods.
    movableTo:   // required — The initial-margin netting sets of other agreements in the run the holding could be re-booked into, as scope/code/item. Recorded for base-case trading lines under an initial-margin item; empty otherwise.
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
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

