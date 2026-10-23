# Finbourne.Sdk.Lusid.Model.FundPartner

A register line of a partnership fund: one partner's commitment and its capital balances at an effective date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The identifier of the investor record this register line belongs to. |
| **DisplayName** | **string** | Optional | The display name of the partner. |
| **CommitmentLineId** | **string** | Required | The identifier of the commitment (register) line. |
| **LusidInstrumentId** | **string** | Required | The LUSID instrument identifier of the register line&#39;s capital-interest instrument. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **IsVehicle** | **bool** | Required | Whether the partner is a vehicle (for example a feeder or parallel fund) rather than an end investor. |
| **PartnerRole** | **string** | Required | The role of the register line. Available values: GPRegister, LPInvestment. |
| **CommitmentCurrency** | **string** | Required | The currency of the partner&#39;s commitment. |
| **Balances** | [FundPartnerBalances](FundPartnerBalances.md) | Required | *No description available.* |
| **ShareOfCommitments** | **decimal** | Required | The partner&#39;s committed capital as a decimal fraction of the fund&#39;s total commitments in the same commitment currency. |
| **AdmittedOn** | **DateTimeOffset?** | Optional | The date the partner was admitted, being the date of their first commitment. |
| **Totals** | [FundPartnersTotals](FundPartnersTotals.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartner(
    investorRecordId: "...",  // required — The identifier of the investor record this register line belongs to.
    displayName: "...",  // optional — The display name of the partner.
    commitmentLineId: "...",  // required — The identifier of the commitment (register) line.
    lusidInstrumentId: "...",  // required — The LUSID instrument identifier of the register line&#39;s capital-interest instrument.
    portfolioId: new ResourceId(...),  // required
    isVehicle: true,  // required — Whether the partner is a vehicle (for example a feeder or parallel fund) rather than an end investor.
    partnerRole: "...",  // required — The role of the register line. Available values: GPRegister, LPInvestment.
    commitmentCurrency: "...",  // required — The currency of the partner&#39;s commitment.
    balances: new FundPartnerBalances(...),  // required
    shareOfCommitments: 0.0d,  // required — The partner&#39;s committed capital as a decimal fraction of the fund&#39;s total commitments in the same commitment currency.
    admittedOn: DateTimeOffset.Now,  // optional — The date the partner was admitted, being the date of their first commitment.
    totals: new FundPartnersTotals(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartner>(json);
```

- [ResourceId](ResourceId.md)
- [FundPartnerBalances](FundPartnerBalances.md)
- [FundPartnersTotals](FundPartnersTotals.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

