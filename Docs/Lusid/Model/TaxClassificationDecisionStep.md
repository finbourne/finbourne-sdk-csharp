# Finbourne.Sdk.Lusid.Model.TaxClassificationDecisionStep

One question the decision tree asked on the way to the leaf.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Order** | **int** | Required | The position of the step in the decision trace, starting at 1. |
| **Rule** | **string** | Required | The decision-tree rule the step evaluated. |
| **Question** | **string** | Required | The question the rule asked of the inputs. |
| **Answer** | **string** | Required | The answer the rule took. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationDecisionStep(
    order: 0,  // required — The position of the step in the decision trace, starting at 1.
    rule: "...",  // required — The decision-tree rule the step evaluated.
    question: "...",  // required — The question the rule asked of the inputs.
    answer: "..."  // required — The answer the rule took.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationDecisionStep>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

