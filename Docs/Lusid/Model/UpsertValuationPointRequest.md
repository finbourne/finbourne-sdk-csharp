# Finbourne.Sdk.Lusid.Model.UpsertValuationPointRequest

A definition for the period you wish to close
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Required | Unique code for the Valuation Point. |
| **DiaryEntryVariant** | **string** | Optional | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |
| **Name** | **string** | Optional | Identifiable Name assigned to the Valuation Point. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the diary entry. |
| **QueryAsAt** | **DateTimeOffset?** | Optional | The query time of the diary entry. Defaults to latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |
| **ApplyClearDown** | **bool** | Optional | Defaults to false. Set to true if you want that the closed period to have the clear down applied. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest. |
| **UpdateInclusionDateNavAdjustments** | **bool** | Optional | Defaults to false. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertValuationPointRequest(
    diaryEntryCode: "...",  // required — Unique code for the Valuation Point.
    diaryEntryVariant: "...",  // optional — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
    name: "...",  // optional — Identifiable Name assigned to the Valuation Point.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the diary entry.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the diary entry. Defaults to latest.
    properties: new Property(...),  // optional — A set of properties for the diary entry.
    applyClearDown: true,  // optional — Defaults to false. Set to true if you want that the closed period to have the clear down applied.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest.
    updateInclusionDateNavAdjustments: true  // optional — Defaults to false. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertValuationPointRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

