# Finbourne.Sdk.Lusid.Model.CoreDateTolerance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReferenceSide** | **string** | Required | Reference side (source of truth). Available values: Left, Right. |
| **Interval** | **string** | Required | The allowed tolerance for date time core rule values, defined as an ISO Period. |
| **Offset** | **string** | Optional | How the interval should be applied to the reference side value. Defaults to Either. Available values: Earlier, Later, Either. |
| **ToleranceType** | **string** | Required | Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. |
| **RuleName** | **string** | Required | The reference name of the rule that this tolerance relaxes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CoreDateTolerance(
    referenceSide: "...",  // required — Reference side (source of truth). Available values: Left, Right.
    interval: "...",  // required — The allowed tolerance for date time core rule values, defined as an ISO Period.
    offset: "...",  // optional — How the interval should be applied to the reference side value. Defaults to Either. Available values: Earlier, Later, Either.
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
var instance = JsonConvert.DeserializeObject<CoreDateTolerance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

