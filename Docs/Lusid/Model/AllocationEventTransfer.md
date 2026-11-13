# Finbourne.Sdk.Lusid.Model.AllocationEventTransfer

One leg of a Transfer Allocation Event: a fraction of a capital interest line moving to another line.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromLineId** | **string** | Required | The identifier of the capital interest line the fraction moves from, as it appears on the register of one of the map&#39;s members. |
| **ToInvestorRecordId** | **string** | Required | The investor record that receives the transferred interest. |
| **ToLineId** | **string** | Required | The identifier of the capital interest line the fraction moves to. Created if it does not exist. |
| **ToPortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Fraction** | **decimal** | Required | The fraction of the source line transferred, greater than zero and at most one. The legs out of one line together move each balance times the sum of their fractions, rounded to the currency&#39;s minor unit; each leg takes its share truncated to the minor unit and the last leg out of the line takes the remainder, so no leg takes more than its share, the legs never move more than the line holds, and fractions summing to one close the line. |
| **PnlSplit** | **string** | Optional | How the profit and loss of the period containing the transfer is split: InterimClose closes the books on the transfer date; DailyProration prorates by days held. Defaults to InterimClose. Available values: InterimClose, DailyProration. |
| **Consideration** | [AllocationEventTransferConsideration](AllocationEventTransferConsideration.md) | Optional | *No description available.* |
| **ConsentReference** | **string** | Optional | A reference to the consent obtained for the transfer, when the fund requires one. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventTransfer(
    fromLineId: "...",  // required — The identifier of the capital interest line the fraction moves from, as it appears on the register of one of the map&#39;s members.
    toInvestorRecordId: "...",  // required — The investor record that receives the transferred interest.
    toLineId: "...",  // required — The identifier of the capital interest line the fraction moves to. Created if it does not exist.
    toPortfolioId: new ResourceId(...),  // optional
    fraction: 0.0d,  // required — The fraction of the source line transferred, greater than zero and at most one. The legs out of one line together move each balance times the sum of their fractions, rounded to the currency&#39;s minor unit; each leg takes its share truncated to the minor unit and the last leg out of the line takes the remainder, so no leg takes more than its share, the legs never move more than the line holds, and fractions summing to one close the line.
    pnlSplit: "...",  // optional — How the profit and loss of the period containing the transfer is split: InterimClose closes the books on the transfer date; DailyProration prorates by days held. Defaults to InterimClose. Available values: InterimClose, DailyProration.
    consideration: new AllocationEventTransferConsideration(...),  // optional
    consentReference: "..."  // optional — A reference to the consent obtained for the transfer, when the fund requires one.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventTransfer>(json);
```

- [ResourceId](ResourceId.md)
- [AllocationEventTransferConsideration](AllocationEventTransferConsideration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

