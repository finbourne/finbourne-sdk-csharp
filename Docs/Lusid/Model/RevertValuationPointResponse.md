# Finbourne.Sdk.Lusid.Model.RevertValuationPointResponse

A Valuation Point reverted to Estimate, with all of its variants. Any variant that finalising the Valuation Point  had rejected is brought back as an Estimate by the revert, and is reported here alongside it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **ValuationPointCode** | **string** | Optional | The code of the Valuation Point. |
| **NavTypeCode** | **string** | Optional | The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with. |
| **Status** | **string** | Required | The status of the Valuation Point. Available values: Undefined, Estimate, Final, Candidate, Rejected, Unofficial. |
| **ApplyClearDown** | **bool** | Optional | Indicates whether a clear down was applied when the Valuation Point was created. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the Valuation Point. |
| **Previous** | [PreviousValuationPoint](PreviousValuationPoint.md) | Optional | *No description available.* |
| **Variants** | [List&lt;EstimateVariant&gt;](EstimateVariant.md) | Optional | The variants of the Estimate Valuation Point.  |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RevertValuationPointResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    valuationPointCode: "...",  // optional — The code of the Valuation Point.
    navTypeCode: "...",  // optional — The navTypeCode of the Fund Calendar Entry. This is the code of the NAV type that this Calendar Entry is associated with.
    status: "...",  // required — The status of the Valuation Point. Available values: Undefined, Estimate, Final, Candidate, Rejected, Unofficial.
    applyClearDown: true,  // optional — Indicates whether a clear down was applied when the Valuation Point was created.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the Valuation Point.
    previous: new PreviousValuationPoint(...),  // optional
    variants: new List<EstimateVariant>(),  // optional — The variants of the Estimate Valuation Point. 
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RevertValuationPointResponse>(json);
```

- [PreviousValuationPoint](PreviousValuationPoint.md)
- [EstimateVariant](EstimateVariant.md) — used in `Variants`
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

