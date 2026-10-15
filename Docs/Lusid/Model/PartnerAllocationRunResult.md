# Finbourne.Sdk.Lusid.Model.PartnerAllocationRunResult

The outcome of a partner allocation run: the pools the period's income was split into and what, if anything,  could not be attributed to a pool.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PeriodStart** | **DateTimeOffset** | Required | The start of the period to allocate, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the period to allocate, inclusive. A valuation point must end on this date. |
| **NavTypeCode** | **string** | Required | The NAV type to allocate under. Defaults to the fund&#39;s primary NAV type. |
| **Status** | **string** | Required | The outcome of the run. Available values: Computed, Booked, DryRun. |
| **RunId** | **string** | Required | The identifier of the run, which prefixes every transaction it books. |
| **Pools** | [List&lt;PartnerAllocationPool&gt;](PartnerAllocationPool.md) | Required | The pools of fund-level amount that were allocated. |
| **Unattributed** | [List&lt;UnattributedAmount&gt;](UnattributedAmount.md) | Required | Fund-level amounts that no pool claimed. |
| **BookedTransactionIds** | **List&lt;string&gt;** | Required | The identifiers of the transactions the run booked, if any. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocationRunResult(
    fundId: new ResourceId(...),  // required
    periodStart: DateTimeOffset.Now,  // required — The start of the period to allocate, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the period to allocate, inclusive. A valuation point must end on this date.
    navTypeCode: "...",  // required — The NAV type to allocate under. Defaults to the fund&#39;s primary NAV type.
    status: "...",  // required — The outcome of the run. Available values: Computed, Booked, DryRun.
    runId: "...",  // required — The identifier of the run, which prefixes every transaction it books.
    pools: new List<PartnerAllocationPool>(),  // required — The pools of fund-level amount that were allocated.
    unattributed: new List<UnattributedAmount>(),  // required — Fund-level amounts that no pool claimed.
    bookedTransactionIds:   // required — The identifiers of the transactions the run booked, if any.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerAllocationRunResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PartnerAllocationPool](PartnerAllocationPool.md) — used in `Pools`
- [UnattributedAmount](UnattributedAmount.md) — used in `Unattributed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

