# Finbourne.Sdk.Lusid.Model.RecResultDecisionUpdate

The decision update within a batch review item. Omitting the object leaves the existing decision  untouched; a null value nullifies it (dissolving any group).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Optional | The decision value. Null nullifies the decision. Available values: Acknowledge, FixAtSource, FixAsGroup, Accept, ForceMatch, Tolerate. |
| **Affirm** | **bool** | Optional | Whether to affirm an existing decision (e.g. after revisions were requested). |
| **CoreRulesExcused** | **List&lt;string&gt;** | Optional | The ruleNames of the core rules excused by a ForceMatch. Identical on every group member; non-null only for ForceMatch. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultDecisionUpdate(
    value: "...",  // optional — The decision value. Null nullifies the decision. Available values: Acknowledge, FixAtSource, FixAsGroup, Accept, ForceMatch, Tolerate.
    affirm: true,  // optional — Whether to affirm an existing decision (e.g. after revisions were requested).
    coreRulesExcused:   // optional — The ruleNames of the core rules excused by a ForceMatch. Identical on every group member; non-null only for ForceMatch.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultDecisionUpdate>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

