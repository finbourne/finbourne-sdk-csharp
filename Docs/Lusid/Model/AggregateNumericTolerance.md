# Finbourne.Sdk.Lusid.Model.AggregateNumericTolerance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReferenceSide** | **string** | Required | Reference side (source of truth). One of: Left, Right. Available values: Left, Right. |
| **AbsoluteThreshold** | **decimal?** | Optional | Numeric tolerance absolute value (allowable diff compared to the reference side value). |
| **RelativeThreshold** | **decimal?** | Optional | Numeric tolerance value as a relative % of the reference value. |
| **ThresholdPriority** | **string** | Required | Whether to apply the GreaterOf or LesserOf the absoluteThreshold vs relativeThreshold. One of: GreaterOf, LesserOf. Available values: GreaterOf, LesserOf. |
| **Offset** | **string** | Optional | How the threshold should be applied to the reference side value. One of: Above, Below, Either. Defaults to Either. Available values: Above, Below, Either. |
| **ToleranceType** | **string** | Required | Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. |
| **RuleName** | **string** | Required | The reference name of the rule that this tolerance relaxes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregateNumericTolerance(
    referenceSide: "...",  // required — Reference side (source of truth). One of: Left, Right. Available values: Left, Right.
    absoluteThreshold: 0.0d,  // optional — Numeric tolerance absolute value (allowable diff compared to the reference side value).
    relativeThreshold: 0.0d,  // optional — Numeric tolerance value as a relative % of the reference value.
    thresholdPriority: "...",  // required — Whether to apply the GreaterOf or LesserOf the absoluteThreshold vs relativeThreshold. One of: GreaterOf, LesserOf. Available values: GreaterOf, LesserOf.
    offset: "...",  // optional — How the threshold should be applied to the reference side value. One of: Above, Below, Either. Defaults to Either. Available values: Above, Below, Either.
    toleranceType: "...",  // required — Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric.
    ruleName: "..."  // required — The reference name of the rule that this tolerance relaxes.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregateNumericTolerance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

