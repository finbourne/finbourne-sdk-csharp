# Finbourne.Sdk.Lusid.Model.RecResultReview

The per-result review axis: the workflow state and the recorded review decision. Always present,  including on Match and Cross.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | The review workflow state: NotRequired, Required or Reviewed. Available values: NotRequired, Required, Reviewed. |
| **Decision** | **string** | Optional | The recorded review decision. Null until a decision is made. Available values: Acknowledge, FixAtSource, FixAsGroup, Accept, ForceMatch, Tolerate. |
| **DecisionGroup** | [RecResultDecisionGroup](RecResultDecisionGroup.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultReview(
    status: "...",  // required — The review workflow state: NotRequired, Required or Reviewed. Available values: NotRequired, Required, Reviewed.
    decision: "...",  // optional — The recorded review decision. Null until a decision is made. Available values: Acknowledge, FixAtSource, FixAsGroup, Accept, ForceMatch, Tolerate.
    decisionGroup: new RecResultDecisionGroup(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultReview>(json);
```

- [RecResultDecisionGroup](RecResultDecisionGroup.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

