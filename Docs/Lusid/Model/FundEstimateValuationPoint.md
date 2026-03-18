# Finbourne.Sdk.Lusid.Model.FundEstimateValuationPoint

> **Inherits from:** [FundCalendarEntries](FundCalendarEntries.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The unique Code of the Calendar Entry. The Calendar Entry, together with the Fund Scope and Code, uniquely identifies a Fund Calendar Entry. |
| **NavTypeCode** | **string** | Required | The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with. |
| **TimelineId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PreviousEntry** | [PreviousFundCalendarEntry](PreviousFundCalendarEntry.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective at of the Calendar Entry. |
| **EntryType** | **string** | Required | The type of the Fund Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark |
| **Status** | **string** | Optional | The status of the Fund Calendar Entry. Can be &#39;Estimate&#39;, &#39;Unofficial&#39; or &#39;Final&#39;. |
| **ApplyClearDown** | **bool** | Optional | Set to true if that closed period should have the clear down applied. |
| **LeaderNavTypeCode** | **string** | Optional | The code of the Nav Type that this Nav Type will follow when set. |
| **Variants** | [List&lt;EstimateVariant&gt;](EstimateVariant.md) | Optional | The variants of the Estimate Valuation Point.  |
| **FundCalendarEntriesType** | **string** | Required | The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark Default: `FundCalendarEntriesTypeEnum.FundEstimateValuationPoint` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundEstimateValuationPoint(
    code: "...",  // required — The unique Code of the Calendar Entry. The Calendar Entry, together with the Fund Scope and Code, uniquely identifies a Fund Calendar Entry.
    navTypeCode: "...",  // required — The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with.
    timelineId: new ResourceId(...),  // optional
    previousEntry: new PreviousFundCalendarEntry(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // optional — The effective at of the Calendar Entry.
    entryType: "...",  // required — The type of the Fund Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark
    status: "...",  // optional — The status of the Fund Calendar Entry. Can be &#39;Estimate&#39;, &#39;Unofficial&#39; or &#39;Final&#39;.
    applyClearDown: true,  // optional — Set to true if that closed period should have the clear down applied.
    leaderNavTypeCode: "...",  // optional — The code of the Nav Type that this Nav Type will follow when set.
    variants: new List<EstimateVariant>(),  // optional — The variants of the Estimate Valuation Point. 
    fundCalendarEntriesType: "..."  // required — The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundEstimateValuationPoint>(json);
```


- [ResourceId](ResourceId.md)
- [PreviousFundCalendarEntry](PreviousFundCalendarEntry.md)
- [EstimateVariant](EstimateVariant.md) — used in `Variants`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

