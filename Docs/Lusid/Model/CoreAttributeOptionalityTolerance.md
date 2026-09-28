# Finbourne.Sdk.Lusid.Model.CoreAttributeOptionalityTolerance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OptionalSide** | **string** | Optional | Which side is allowed to have no value while still attempting to match. One of: Left, Right, Either. Defaults to Either. Available values: Left, Right, Either. |
| **ToleranceType** | **string** | Required | Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. |
| **RuleName** | **string** | Required | The reference name of the rule that this tolerance relaxes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CoreAttributeOptionalityTolerance(
    optionalSide: "...",  // optional — Which side is allowed to have no value while still attempting to match. One of: Left, Right, Either. Defaults to Either. Available values: Left, Right, Either.
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
var instance = JsonConvert.DeserializeObject<CoreAttributeOptionalityTolerance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

