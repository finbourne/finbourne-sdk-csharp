# Finbourne.Sdk.Lusid.Model.CategorySettlementStatus

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | The Status of the settlement category - &#39;Settled&#39;, &#39;Part Settled&#39; or &#39;Unsettled&#39;. |
| **IsOverdue** | **bool** | Required | Whether the category has any overdue movements |
| **Problems** | [List&lt;SettlementProblem&gt;](SettlementProblem.md) | Required | Instruction level detail of rejected or invalid settlement instructions |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CategorySettlementStatus(
    status: "...",  // required — The Status of the settlement category - &#39;Settled&#39;, &#39;Part Settled&#39; or &#39;Unsettled&#39;.
    isOverdue: true,  // required — Whether the category has any overdue movements
    problems: new List<SettlementProblem>()  // required — Instruction level detail of rejected or invalid settlement instructions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CategorySettlementStatus>(json);
```

- [SettlementProblem](SettlementProblem.md) — used in `Problems`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

