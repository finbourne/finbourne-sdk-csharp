# Finbourne.Sdk.Lusid.Model.ValuationPoint

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **ValuationPointCode** | **string** | Optional | The code of the Valuation Point. |
| **Variant** | **string** | Optional | The Variant name for the Valuation Point. |
| **Name** | **string** | Optional | Identifiable Name assigned to the Valuation Point. |
| **Status** | **string** | Required | The status of the Valuation Point. Available values: Undefined, Estimate, Final, Candidate, Unofficial, Rejected. |
| **ApplyClearDown** | **bool** | Optional | Indicates whether a clear down was applied when the Valuation Point was created. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the Valuation Point. |
| **QueryAsAt** | **DateTimeOffset** | Optional | The AsAt time of the Valuation Point. This is the AsAt time that will be used when requests are made using the entry. |
| **HoldingsAsAt** | **DateTimeOffset** | Optional | The AsAt time used for building holdings in the Valuation Point. |
| **ValuationAsAt** | **DateTimeOffset** | Optional | The AsAt time used for performing valuations in the Valuation Point. |
| **Previous** | [PreviousValuationPoint](PreviousValuationPoint.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Valuation Point properties. These are from the &#39;DiaryEntry&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPoint(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    valuationPointCode: "...",  // optional — The code of the Valuation Point.
    variant: "...",  // optional — The Variant name for the Valuation Point.
    name: "...",  // optional — Identifiable Name assigned to the Valuation Point.
    status: "...",  // required — The status of the Valuation Point. Available values: Undefined, Estimate, Final, Candidate, Unofficial, Rejected.
    applyClearDown: true,  // optional — Indicates whether a clear down was applied when the Valuation Point was created.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the Valuation Point.
    queryAsAt: DateTimeOffset.Now,  // optional — The AsAt time of the Valuation Point. This is the AsAt time that will be used when requests are made using the entry.
    holdingsAsAt: DateTimeOffset.Now,  // optional — The AsAt time used for building holdings in the Valuation Point.
    valuationAsAt: DateTimeOffset.Now,  // optional — The AsAt time used for performing valuations in the Valuation Point.
    previous: new PreviousValuationPoint(...),  // optional
    properties: new Property(...),  // optional — The Valuation Point properties. These are from the &#39;DiaryEntry&#39; domain.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPoint>(json);
```

- [PreviousValuationPoint](PreviousValuationPoint.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

