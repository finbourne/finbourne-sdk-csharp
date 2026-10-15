# Finbourne.Sdk.Lusid.Model.EligibleCollateralScheduleRequest

The request used to create an Eligible Collateral Schedule.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Eligible Collateral Schedule. |
| **Description** | **string** | Optional | A description of the Eligible Collateral Schedule. Optional. |
| **Rows** | [List&lt;EligibleCollateralRowRequest&gt;](EligibleCollateralRowRequest.md) | Required | The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Eligible Collateral Schedule. Filterable. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime from which the Eligible Collateral Schedule applies. Defaults to the beginning of time if not specified, so that the schedule is visible at every effective datetime. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibleCollateralScheduleRequest(
    code: "...",  // required — The code of the Eligible Collateral Schedule.
    description: "...",  // optional — A description of the Eligible Collateral Schedule. Optional.
    rows: new List<EligibleCollateralRowRequest>(),  // required — The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows.
    properties: new Property(...),  // optional — A set of properties to decorate onto the Eligible Collateral Schedule. Filterable.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime from which the Eligible Collateral Schedule applies. Defaults to the beginning of time if not specified, so that the schedule is visible at every effective datetime.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibleCollateralScheduleRequest>(json);
```

- [EligibleCollateralRowRequest](EligibleCollateralRowRequest.md) — used in `Rows`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

