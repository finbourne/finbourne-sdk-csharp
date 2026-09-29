# Finbourne.Sdk.Lusid.Model.CoreStringCrossTolerance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReferenceValue** | **string** | Required | The value for the reference side. |
| **CrossValue** | **string** | Required | The value for the side other than the reference one. |
| **ReferenceSide** | **string** | Optional | Reference side (source of truth). Available values: Left, Right, Either. |
| **ToleranceType** | **string** | Required | Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. |
| **RuleName** | **string** | Required | The reference name of the rule that this tolerance relaxes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CoreStringCrossTolerance(
    referenceValue: "...",  // required — The value for the reference side.
    crossValue: "...",  // required — The value for the side other than the reference one.
    referenceSide: "...",  // optional — Reference side (source of truth). Available values: Left, Right, Either.
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
var instance = JsonConvert.DeserializeObject<CoreStringCrossTolerance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

