# Finbourne.Sdk.Lusid.Model.PartnerAllocationRunRequest

The request to allocate a period's income summary to the partners of a partnership fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodStart** | **DateTimeOffset** | Required | The start of the period to allocate, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the period to allocate, inclusive. A valuation point must end on this date. |
| **NavTypeCode** | **string** | Optional | The NAV type to allocate under. Defaults to the fund&#39;s primary NAV type. |
| **DryRun** | **bool** | Optional | When true, the allocation is computed and returned but nothing is booked. |
| **Correction** | **bool** | Optional | When true, a period that has already been allocated may be re-allocated. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocationRunRequest(
    periodStart: DateTimeOffset.Now,  // required — The start of the period to allocate, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the period to allocate, inclusive. A valuation point must end on this date.
    navTypeCode: "...",  // optional — The NAV type to allocate under. Defaults to the fund&#39;s primary NAV type.
    dryRun: true,  // optional — When true, the allocation is computed and returned but nothing is booked.
    correction: true  // optional — When true, a period that has already been allocated may be re-allocated.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerAllocationRunRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

