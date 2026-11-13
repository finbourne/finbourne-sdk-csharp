# Finbourne.Sdk.Lusid.Model.TaxProvision

The deferred tax provision struck for a fund at a valuation point: the realised and notionally realised  (deemed disposal) gains it is built from, the indexation and loss relief applied, the rate, the resulting  provision amount, its movement since the previous valuation point and, once approved, who approved it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Fund** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **NavTypeCode** | **string** | Required | The NAV type the provision was struck for. |
| **DiaryEntryCode** | **string** | Required | The diary entry code of the valuation point the provision was struck at. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date of the valuation point the provision was struck at. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which this version of the provision was recorded. |
| **Status** | **string** | Required | Whether the provision is an Estimate or has been Approved. An approved provision has been posted to the fund as an accrual. |
| **RealisedGains** | **decimal** | Required | The chargeable gains realised by disposals since the start of the tax period, after indexation allowance. |
| **UnrealisedGains** | **decimal** | Required | The chargeable gains that would arise on a notional deemed disposal of the fund&#39;s holdings at the valuation point. |
| **IndexationAllowance** | **decimal** | Required | The indexation allowance taken against the gains in this provision. |
| **LossesBroughtForward** | **decimal** | Required | The allowable losses standing at the start of the tax period and available to offset gains. |
| **LossesUsed** | **decimal** | Required | The losses brought forward that were used against the gains in this provision. |
| **LossesCarriedForward** | **decimal** | Required | The allowable losses remaining after this provision, to be carried forward to the next tax period. Only realised losses are carried; a notional loss on the deemed disposal is not. |
| **RateApplied** | **decimal** | Required | The tax rate applied to the net chargeable gains to arrive at the provision amount. |
| **ProvisionAmount** | **decimal** | Required | The deferred tax provision amount at the valuation point. |
| **Movement** | [TaxProvisionMovement](TaxProvisionMovement.md) | Required | *No description available.* |
| **ApprovedBy** | **string** | Optional | The user who approved the provision, if it has been approved. |
| **ApprovedAt** | **DateTimeOffset?** | Optional | The asAt datetime at which the provision was approved, if it has been approved. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxProvision(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    fund: new ResourceId(...),  // required
    navTypeCode: "...",  // required — The NAV type the provision was struck for.
    diaryEntryCode: "...",  // required — The diary entry code of the valuation point the provision was struck at.
    effectiveAt: DateTimeOffset.Now,  // required — The effective date of the valuation point the provision was struck at.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime at which this version of the provision was recorded.
    status: "...",  // required — Whether the provision is an Estimate or has been Approved. An approved provision has been posted to the fund as an accrual.
    realisedGains: 0.0d,  // required — The chargeable gains realised by disposals since the start of the tax period, after indexation allowance.
    unrealisedGains: 0.0d,  // required — The chargeable gains that would arise on a notional deemed disposal of the fund&#39;s holdings at the valuation point.
    indexationAllowance: 0.0d,  // required — The indexation allowance taken against the gains in this provision.
    lossesBroughtForward: 0.0d,  // required — The allowable losses standing at the start of the tax period and available to offset gains.
    lossesUsed: 0.0d,  // required — The losses brought forward that were used against the gains in this provision.
    lossesCarriedForward: 0.0d,  // required — The allowable losses remaining after this provision, to be carried forward to the next tax period. Only realised losses are carried; a notional loss on the deemed disposal is not.
    rateApplied: 0.0d,  // required — The tax rate applied to the net chargeable gains to arrive at the provision amount.
    provisionAmount: 0.0d,  // required — The deferred tax provision amount at the valuation point.
    movement: new TaxProvisionMovement(...),  // required
    approvedBy: "...",  // optional — The user who approved the provision, if it has been approved.
    approvedAt: DateTimeOffset.Now,  // optional — The asAt datetime at which the provision was approved, if it has been approved.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxProvision>(json);
```

- [ResourceId](ResourceId.md)
- [TaxProvisionMovement](TaxProvisionMovement.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

