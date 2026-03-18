# Finbourne.Sdk.Lusid.Model.ValuationPointOverview

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **DiaryEntryCode** | **string** | Required | The code for the Valuation Point. |
| **DiaryEntryVariant** | **string** | Optional | The Variant for the Valuation Point. Together with the valuation point code marks the unique branch for the NavType. |
| **EffectiveFrom** | **DateTimeOffset** | Required | The effective time of the last Valuation Point. |
| **EffectiveTo** | **DateTimeOffset** | Required | The effective time of the current Valuation Point. |
| **QueryAsAt** | **DateTimeOffset** | Optional | The query time of the Valuation Point. Defaults to latest. |
| **Type** | **string** | Required | The type of the diary entry. This is &#39;ValuationPoint&#39;. |
| **Status** | **string** | Required | The status of the Valuation Point. Can be &#39;Estimate&#39;, &#39;Candidate&#39; or &#39;Final&#39;. |
| **Gav** | **decimal** | Required | The Gross Asset Value of the Fund or Share Class at the Valuation Point. This is effectively a summation of all Trial balance entries linked to accounts of types &#39;Asset&#39; and &#39;Liabilities&#39;. |
| **Nav** | **decimal** | Required | The Net Asset Value of the Fund or Share Class at the Valuation Point. This represents the GAV with any fees applied in the period. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Fee properties. These will be from the &#39;Fee&#39; domain. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointOverview(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    diaryEntryCode: "...",  // required — The code for the Valuation Point.
    diaryEntryVariant: "...",  // optional — The Variant for the Valuation Point. Together with the valuation point code marks the unique branch for the NavType.
    effectiveFrom: DateTimeOffset.Now,  // required — The effective time of the last Valuation Point.
    effectiveTo: DateTimeOffset.Now,  // required — The effective time of the current Valuation Point.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the Valuation Point. Defaults to latest.
    type: "...",  // required — The type of the diary entry. This is &#39;ValuationPoint&#39;.
    status: "...",  // required — The status of the Valuation Point. Can be &#39;Estimate&#39;, &#39;Candidate&#39; or &#39;Final&#39;.
    gav: 0.0d,  // required — The Gross Asset Value of the Fund or Share Class at the Valuation Point. This is effectively a summation of all Trial balance entries linked to accounts of types &#39;Asset&#39; and &#39;Liabilities&#39;.
    nav: 0.0d,  // required — The Net Asset Value of the Fund or Share Class at the Valuation Point. This represents the GAV with any fees applied in the period.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest.
    properties: new Property(...),  // optional — The Fee properties. These will be from the &#39;Fee&#39; domain.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointOverview>(json);
```

- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

