# Finbourne.Sdk.Lusid.Model.ToleranceBase

Base class for the tolerances that relax how strictly a matching rule compares its two sides. Polymorphic  by ToleranceType; each supported type has a corresponding inherited class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ToleranceType** | **string** | Required | Polymorphic discriminator. Supported types: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. Available values: CoreStringCross, CoreAttributeOptionality, CoreDateTolerance, Numeric. |
| **RuleName** | **string** | Required | The reference name of the rule that this tolerance relaxes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ToleranceBase(
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
var instance = JsonConvert.DeserializeObject<ToleranceBase>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

