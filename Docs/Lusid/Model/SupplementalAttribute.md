# Finbourne.Sdk.Lusid.Model.SupplementalAttribute

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Required | The reference name of the supplemental attribute. |
| **LeftFormula** | **string** | Required | Derivation formula evaluated against the left side of the reconciliation. |
| **RightFormula** | **string** | Required | Derivation formula evaluated against the right side of the reconciliation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SupplementalAttribute(
    attributeName: "...",  // required — The reference name of the supplemental attribute.
    leftFormula: "...",  // required — Derivation formula evaluated against the left side of the reconciliation.
    rightFormula: "..."  // required — Derivation formula evaluated against the right side of the reconciliation.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupplementalAttribute>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

