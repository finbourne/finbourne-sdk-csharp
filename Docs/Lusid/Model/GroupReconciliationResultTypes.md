# Finbourne.Sdk.Lusid.Model.GroupReconciliationResultTypes

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountMatch** | **int** | Required | The number of comparison results of resultType \&quot;Match\&quot; with this instanceId and reconciliationType |
| **LinkMatches** | [Link](Link.md) | Required | *No description available.* |
| **CountPartialMatch** | **int** | Required | The number of comparison results of resultType \&quot;PartialMatch\&quot; with this instanceId and reconciliationType |
| **LinkPartialMatches** | [Link](Link.md) | Required | *No description available.* |
| **CountBreak** | **int** | Required | The number of comparison results of resultType \&quot;Break\&quot; with this instanceId and reconciliationType |
| **LinkBreaks** | [Link](Link.md) | Required | *No description available.* |
| **CountResolved** | **int** | Required | The number of comparison results of resultType \&quot;Resolved\&quot; with this instanceId and reconciliationType |
| **LinkResolved** | [Link](Link.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationResultTypes(
    countMatch: 0,  // required — The number of comparison results of resultType \&quot;Match\&quot; with this instanceId and reconciliationType
    linkMatches: new Link(...),  // required
    countPartialMatch: 0,  // required — The number of comparison results of resultType \&quot;PartialMatch\&quot; with this instanceId and reconciliationType
    linkPartialMatches: new Link(...),  // required
    countBreak: 0,  // required — The number of comparison results of resultType \&quot;Break\&quot; with this instanceId and reconciliationType
    linkBreaks: new Link(...),  // required
    countResolved: 0,  // required — The number of comparison results of resultType \&quot;Resolved\&quot; with this instanceId and reconciliationType
    linkResolved: new Link(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationResultTypes>(json);
```

- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

