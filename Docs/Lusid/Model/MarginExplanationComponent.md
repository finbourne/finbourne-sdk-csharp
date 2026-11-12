# Finbourne.Sdk.Lusid.Model.MarginExplanationComponent

One step in the working behind a margin figure: a value and, unless it is a leaf, the arithmetic over its  sub-components that gives it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | Identifies the component within its explanation: its position in the tree as dot-separated indexes from the root, such as 0.1.3, the first index being the root&#39;s place among the explanation&#39;s components. |
| **Component** | **string** | Required | A stable name for what the component is, such as PvInBase. A component whose rows the caller may not read is named Redacted. |
| **DisplayName** | **string** | Required | A human-readable name for the component. |
| **Type** | **string** | Required | How the component takes its value. One of DerivedProperty, PartialFormula, Variable or Literal. |
| **Value** | **decimal?** | Optional | The figure the engine used for the component, as it was computed. Null where the component has none or, for a redacted component, where the rows it stands in for do not share a unit and currency. |
| **Unit** | **string** | Optional | What the value measures. One of Currency, Percentage, Factor, Units or Years. Null where the value is unitless. |
| **Currency** | **string** | Optional | The currency of a Currency value when it is not the explanation&#39;s currency. |
| **DerivationFormula** | **string** | Optional | Plain arithmetic over the sub-components that gives the component&#39;s value. Null for a component with no sub-components. |
| **SubComponents** | [List&lt;MarginExplanationComponent&gt;](MarginExplanationComponent.md) | Optional | The components the derivation formula reads. Null for a component that cannot be broken down further. |
| **Redacted** | **bool?** | Optional | True for a component that stands in for the working of portfolios the caller may not read. The caller sees that those portfolios contributed and, when their rows share a unit and currency, their combined value, so that the parent still adds up to the figure; never which portfolios or holdings they were. Null otherwise. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginExplanationComponent(
    id: "...",  // required — Identifies the component within its explanation: its position in the tree as dot-separated indexes from the root, such as 0.1.3, the first index being the root&#39;s place among the explanation&#39;s components.
    component: "...",  // required — A stable name for what the component is, such as PvInBase. A component whose rows the caller may not read is named Redacted.
    displayName: "...",  // required — A human-readable name for the component.
    type: "...",  // required — How the component takes its value. One of DerivedProperty, PartialFormula, Variable or Literal.
    value: 0.0d,  // optional — The figure the engine used for the component, as it was computed. Null where the component has none or, for a redacted component, where the rows it stands in for do not share a unit and currency.
    unit: "...",  // optional — What the value measures. One of Currency, Percentage, Factor, Units or Years. Null where the value is unitless.
    currency: "...",  // optional — The currency of a Currency value when it is not the explanation&#39;s currency.
    derivationFormula: "...",  // optional — Plain arithmetic over the sub-components that gives the component&#39;s value. Null for a component with no sub-components.
    subComponents: new List<MarginExplanationComponent>(),  // optional — The components the derivation formula reads. Null for a component that cannot be broken down further.
    redacted: true  // optional — True for a component that stands in for the working of portfolios the caller may not read. The caller sees that those portfolios contributed and, when their rows share a unit and currency, their combined value, so that the parent still adds up to the figure; never which portfolios or holdings they were. Null otherwise.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginExplanationComponent>(json);
```

- [MarginExplanationComponent](MarginExplanationComponent.md) — used in `SubComponents`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

