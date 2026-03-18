# Finbourne.Sdk.Lusid.Model.FinalisedValuationPoint

> **Inherits from:** [FundCalendarEntries](FundCalendarEntries.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The unique code of the Valuation Point. The Valuation Point Code, together with the Fund Scope and Code, uniquely identifies a Valuation Point. |
| **FinalisedFromVariant** | **string** | Optional | The variant of the Estimate Valuation Point that was finalised to create the Finalised Valuation Point. |
| **DisplayName** | **string** | Required | The name of the Fund Calendar entry. |
| **Description** | **string** | Optional | A description for the Fund Calendar entry. |
| **NavTypeCode** | **string** | Required | The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with. |
| **TimelineId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PreviousEntry** | [PreviousFundCalendarEntry](PreviousFundCalendarEntry.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective at of the Calendar Entry. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime for the Calendar Entry. |
| **EntryType** | **string** | Required | The type of the Fund Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark |
| **Status** | **string** | Optional | The status of the Fund Calendar Entry. Can be &#39;Estimate&#39;, &#39;Unofficial&#39; or &#39;Final&#39;. |
| **ApplyClearDown** | **bool** | Required | Set to true if that closed period should have the clear down applied. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties for the Calendar Entry. These will be from the &#39;ClosedPeriod&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime. |
| **LeaderNavTypeCode** | **string** | Optional | The code of the Nav Type that this Nav Type will follow when set. |
| **FundCalendarEntriesType** | **string** | Required | The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark Default: `FundCalendarEntriesTypeEnum.FinalisedValuationPoint` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FinalisedValuationPoint(
    code: "...",  // required — The unique code of the Valuation Point. The Valuation Point Code, together with the Fund Scope and Code, uniquely identifies a Valuation Point.
    finalisedFromVariant: "...",  // optional — The variant of the Estimate Valuation Point that was finalised to create the Finalised Valuation Point.
    displayName: "...",  // required — The name of the Fund Calendar entry.
    description: "...",  // optional — A description for the Fund Calendar entry.
    navTypeCode: "...",  // required — The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with.
    timelineId: new ResourceId(...),  // optional
    previousEntry: new PreviousFundCalendarEntry(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // optional — The effective at of the Calendar Entry.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime for the Calendar Entry.
    entryType: "...",  // required — The type of the Fund Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark
    status: "...",  // optional — The status of the Fund Calendar Entry. Can be &#39;Estimate&#39;, &#39;Unofficial&#39; or &#39;Final&#39;.
    applyClearDown: true,  // required — Set to true if that closed period should have the clear down applied.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest.
    properties: new Property(...),  // optional — The properties for the Calendar Entry. These will be from the &#39;ClosedPeriod&#39; domain.
    varVersion: new ModelVersion(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime.
    leaderNavTypeCode: "...",  // optional — The code of the Nav Type that this Nav Type will follow when set.
    fundCalendarEntriesType: "..."  // required — The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FinalisedValuationPoint>(json);
```


- [ResourceId](ResourceId.md)
- [PreviousFundCalendarEntry](PreviousFundCalendarEntry.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

