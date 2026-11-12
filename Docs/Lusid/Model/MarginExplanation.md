# Finbourne.Sdk.Lusid.Model.MarginExplanation

How the margin figures of a call or a line were arrived at: the working behind each figure as a tree of components,  with the working of portfolios the caller may not read replaced by a redacted component.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The URI of this explanation. |
| **RunId** | **string** | Required | The run whose figures are explained. |
| **AgreementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Item** | **string** | Optional | The margin item of the call explained or, for a line, of the line. |
| **MarginType** | **string** | Optional | The margin type of the call explained. Null when a line is explained. |
| **Direction** | **string** | Optional | Who posts under the call explained: WePost, TheyPost or None. Null when a line is explained. |
| **LineKey** | **string** | Optional | The key of the line explained. Null when a call is explained. |
| **Currency** | **string** | Required | The agreement&#39;s base currency, in which a component&#39;s value is expressed unless the component names another. |
| **Scenario** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Components** | [List&lt;MarginExplanationComponent&gt;](MarginExplanationComponent.md) | Required | The working behind each figure explained, one root component per figure: for a call its required amount, named InitialMarginRequired, and for a line each figure asked for that the run explained, named VariationMargin or InitialMargin. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginExplanation(
    href: "...",  // optional — The URI of this explanation.
    runId: "...",  // required — The run whose figures are explained.
    agreementId: new ResourceId(...),  // required
    item: "...",  // optional — The margin item of the call explained or, for a line, of the line.
    marginType: "...",  // optional — The margin type of the call explained. Null when a line is explained.
    direction: "...",  // optional — Who posts under the call explained: WePost, TheyPost or None. Null when a line is explained.
    lineKey: "...",  // optional — The key of the line explained. Null when a call is explained.
    currency: "...",  // required — The agreement&#39;s base currency, in which a component&#39;s value is expressed unless the component names another.
    scenario: new ResourceId(...),  // optional
    components: new List<MarginExplanationComponent>()  // required — The working behind each figure explained, one root component per figure: for a call its required amount, named InitialMarginRequired, and for a line each figure asked for that the run explained, named VariationMargin or InitialMargin.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginExplanation>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [MarginExplanationComponent](MarginExplanationComponent.md) — used in `Components`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

