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
| **Pools** | [List&lt;PartnerAllocationPool&gt;](PartnerAllocationPool.md) | Required | The pools of fund-level amount that were allocated, in the allocation bucket set&#39;s bucket order with any tag pools after. |
| **Unattributed** | [List&lt;UnattributedAmount&gt;](UnattributedAmount.md) | Required | Always empty: every profit and loss line is now pooled or the run is refused. Kept for one release. |
| **BookedTransactionIds** | **List&lt;string&gt;** | Required | The identifiers of the transactions the run booked, if any. |
| **Warnings** | **List&lt;string&gt;** | Optional | What the run noticed but did not refuse, for example an excluded investor record that is not on the register at the period end. |
| **IgnoredTags** | [List&lt;IgnoredDistributionTag&gt;](IgnoredDistributionTag.md) | Optional | The distribution character tags the run did not pool by, by account. |
| **AccruedFees** | [List&lt;AccruedFeeLine&gt;](AccruedFeeLine.md) | Optional | The management fees accrued per partner in the period, which the accrual allocates and the run therefore leaves out of the pools. |


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
    pools: new List<PartnerAllocationPool>(),  // required — The pools of fund-level amount that were allocated, in the allocation bucket set&#39;s bucket order with any tag pools after.
    unattributed: new List<UnattributedAmount>(),  // required — Always empty: every profit and loss line is now pooled or the run is refused. Kept for one release.
    bookedTransactionIds: ,  // required — The identifiers of the transactions the run booked, if any.
    warnings: ,  // optional — What the run noticed but did not refuse, for example an excluded investor record that is not on the register at the period end.
    ignoredTags: new List<IgnoredDistributionTag>(),  // optional — The distribution character tags the run did not pool by, by account.
    accruedFees: new List<AccruedFeeLine>()  // optional — The management fees accrued per partner in the period, which the accrual allocates and the run therefore leaves out of the pools.
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
- [IgnoredDistributionTag](IgnoredDistributionTag.md) — used in `IgnoredTags`
- [AccruedFeeLine](AccruedFeeLine.md) — used in `AccruedFees`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

