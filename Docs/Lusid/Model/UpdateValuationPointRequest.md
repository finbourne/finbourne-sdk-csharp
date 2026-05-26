# Finbourne.Sdk.Lusid.Model.UpdateValuationPointRequest

A definition for the period you wish to close
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Required | Unique code for the Valuation Point. |
| **DiaryEntryVariant** | **string** | Required | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |
| **Name** | **string** | Optional | Identifiable Name assigned to the Valuation Point. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |
| **ApplyClearDown** | **bool?** | Optional | Defaults to false. Set to true if you want that the closed period to have the clear down applied. |
| **UpdateInclusionDateNavAdjustments** | **bool?** | Optional | Defaults to false. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateValuationPointRequest(
    diaryEntryCode: "...",  // required — Unique code for the Valuation Point.
    diaryEntryVariant: "...",  // required — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
    name: "...",  // optional — Identifiable Name assigned to the Valuation Point.
    properties: new Property(...),  // optional — A set of properties for the diary entry.
    applyClearDown: true,  // optional — Defaults to false. Set to true if you want that the closed period to have the clear down applied.
    updateInclusionDateNavAdjustments: true  // optional — Defaults to false. Set to true if you have the required licence and want the InclusionDate property values to be used to determine whether items should be automatically included in the post close activities.
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

