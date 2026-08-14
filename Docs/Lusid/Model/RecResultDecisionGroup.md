# Finbourne.Sdk.Lusid.Model.RecResultDecisionGroup

The group-decision detail carried on every member of a FixAsGroup or ForceMatch decision.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupNumber** | **int** | Required | Server-allocated, monotonic group number, unique within the RecResultSet and never reused. |
| **CoreRulesExcused** | **List&lt;string&gt;** | Optional | The ruleNames of the core rules excused by a ForceMatch. Identical on every group member; non-null only for ForceMatch. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultDecisionGroup(
    groupNumber: 0,  // required — Server-allocated, monotonic group number, unique within the RecResultSet and never reused.
    coreRulesExcused:   // optional — The ruleNames of the core rules excused by a ForceMatch. Identical on every group member; non-null only for ForceMatch.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultDecisionGroup>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

