# Finbourne.Sdk.Lusid.Model.UpsertEligibleCollateralScheduleRequest

The request used to create or replace the definition of an Eligible Collateral Schedule from an effective date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | A description of the Eligible Collateral Schedule. Optional. |
| **Rows** | [List&lt;EligibleCollateralRowRequest&gt;](EligibleCollateralRowRequest.md) | Required | The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Eligible Collateral Schedule. Filterable. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime or cut label from which the change applies. Defaults to the current LUSID system datetime if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertEligibleCollateralScheduleRequest(
    description: "...",  // optional — A description of the Eligible Collateral Schedule. Optional.
    rows: new List<EligibleCollateralRowRequest>(),  // required — The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows.
    properties: new Property(...),  // optional — A set of properties to decorate onto the Eligible Collateral Schedule. Filterable.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime or cut label from which the change applies. Defaults to the current LUSID system datetime if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertEligibleCollateralScheduleRequest>(json);
```

- [EligibleCollateralRowRequest](EligibleCollateralRowRequest.md) — used in `Rows`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

