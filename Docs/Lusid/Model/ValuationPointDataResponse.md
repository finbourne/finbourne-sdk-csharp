# Finbourne.Sdk.Lusid.Model.ValuationPointDataResponse

The Valuation Point Data Response for the Fund and specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Type** | **string** | Required | The Type of the associated Diary Entry (&#39;PeriodBoundary&#39;,&#39;ValuationPoint&#39;,&#39;Other&#39; or &#39;Adhoc&#39; when a diary entry wasn&#39;t used). |
| **Status** | **string** | Required | The status of a Diary Entry of Type &#39;ValuationPoint&#39;. Defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised. The status of a Diary Entry becomes &#39;Unofficial&#39; when a diary entry wasn&#39;t used. |
| **FundDetails** | [FundDetails](FundDetails.md) | Required | *No description available.* |
| **FundValuationPointData** | [FundValuationPointData](FundValuationPointData.md) | Required | *No description available.* |
| **ShareClassData** | [List&lt;ShareClassData&gt;](ShareClassData.md) | Required | The data for all share classes in fund. Share classes are identified by their short codes. |
| **ValuationPointCode** | **string** | Optional | The code of the valuation point. |
| **PreviousValuationPointCode** | **string** | Optional | The code of the previous valuation point. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointDataResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    type: "...",  // required — The Type of the associated Diary Entry (&#39;PeriodBoundary&#39;,&#39;ValuationPoint&#39;,&#39;Other&#39; or &#39;Adhoc&#39; when a diary entry wasn&#39;t used).
    status: "...",  // required — The status of a Diary Entry of Type &#39;ValuationPoint&#39;. Defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised. The status of a Diary Entry becomes &#39;Unofficial&#39; when a diary entry wasn&#39;t used.
    fundDetails: new FundDetails(...),  // required
    fundValuationPointData: new FundValuationPointData(...),  // required
    shareClassData: new List<ShareClassData>(),  // required — The data for all share classes in fund. Share classes are identified by their short codes.
    valuationPointCode: "...",  // optional — The code of the valuation point.
    previousValuationPointCode: "...",  // optional — The code of the previous valuation point.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointDataResponse>(json);
```

- [FundDetails](FundDetails.md)
- [FundValuationPointData](FundValuationPointData.md)
- [ShareClassData](ShareClassData.md) — used in `ShareClassData`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

