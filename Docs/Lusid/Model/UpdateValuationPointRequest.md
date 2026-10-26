# Finbourne.Sdk.Lusid.Model.UpdateValuationPointRequest

A definition for the period you wish to close
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ValuationPointCode** | **string** | Required | Unique code for the Valuation Point. |
| **Variant** | **string** | Optional | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |
| **Name** | **string** | Optional | Identifiable Name assigned to the Valuation Point. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |
| **ApplyClearDown** | **bool?** | Optional | Defaults to null. Set to true if you want the closed period to have the clear down applied. |
| **UpdateInclusionDateNavAdjustments** | **bool?** | Optional | Defaults to null. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities. |
| **PricingMethodologyOverride** | [PricingMethodologyOverrideRequest](PricingMethodologyOverrideRequest.md) | Optional | *No description available.* |
| **BucketSetSeeds** | [List&lt;BucketSetSeedRequest&gt;](BucketSetSeedRequest.md) | Optional | Defaults to null. The closing balances to seed for bucket sets at this estimate valuation point, at most one per bucket set. They replace the seeds this variant of the valuation point had, and none removes them. Null leaves them as they are. While the valuation point is an estimate, each seeded bucket set&#39;s flow bucket values are its seed; finalising the valuation point stores them, and the next valuation point opens from them. A bucket set can only be seeded when the previous final valuation point has no values for it. The seed is trusted input: it is not reconciled to the share class NAVs. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateValuationPointRequest(
    valuationPointCode: "...",  // required — Unique code for the Valuation Point.
    variant: "...",  // optional — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
    name: "...",  // optional — Identifiable Name assigned to the Valuation Point.
    properties: new Property(...),  // optional — A set of properties for the diary entry.
    applyClearDown: true,  // optional — Defaults to null. Set to true if you want the closed period to have the clear down applied.
    updateInclusionDateNavAdjustments: true,  // optional — Defaults to null. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities.
    pricingMethodologyOverride: new PricingMethodologyOverrideRequest(...),  // optional
    bucketSetSeeds: new List<BucketSetSeedRequest>()  // optional — Defaults to null. The closing balances to seed for bucket sets at this estimate valuation point, at most one per bucket set. They replace the seeds this variant of the valuation point had, and none removes them. Null leaves them as they are. While the valuation point is an estimate, each seeded bucket set&#39;s flow bucket values are its seed; finalising the valuation point stores them, and the next valuation point opens from them. A bucket set can only be seeded when the previous final valuation point has no values for it. The seed is trusted input: it is not reconciled to the share class NAVs.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateValuationPointRequest>(json);
```

- [Property](Property.md) — used in `Properties`
- [PricingMethodologyOverrideRequest](PricingMethodologyOverrideRequest.md)
- [BucketSetSeedRequest](BucketSetSeedRequest.md) — used in `BucketSetSeeds`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

