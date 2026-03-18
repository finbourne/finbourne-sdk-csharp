# Finbourne.Sdk.Lusid.Model.DerivedPropertyComponent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Component** | **string** | Optional | The component of the formula which is being evaluated. |
| **DisplayName** | **string** | Optional | The display name of the component being evaluated. |
| **Type** | **string** | Optional | The type of the formula component. This can be a Literal, Variable, DerivedProperty, or PartialFormula. |
| **Value** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **DerivationFormula** | **string** | Optional | The derivation formula of the component. This field will only be populated if the component is a derived property. |
| **SubComponents** | [List&lt;DerivedPropertyComponent&gt;](DerivedPropertyComponent.md) | Optional | Any sub-components of this formula. If this formula cannot be further decomposed, this collection will be null. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DerivedPropertyComponent(
    component: "...",  // optional — The component of the formula which is being evaluated.
    displayName: "...",  // optional — The display name of the component being evaluated.
    type: "...",  // optional — The type of the formula component. This can be a Literal, Variable, DerivedProperty, or PartialFormula.
    value: new PropertyValue(...),  // optional
    derivationFormula: "...",  // optional — The derivation formula of the component. This field will only be populated if the component is a derived property.
    subComponents: new List<DerivedPropertyComponent>(),  // optional — Any sub-components of this formula. If this formula cannot be further decomposed, this collection will be null.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DerivedPropertyComponent>(json);
```

- [PropertyValue](PropertyValue.md)
- [DerivedPropertyComponent](DerivedPropertyComponent.md) — used in `SubComponents`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

