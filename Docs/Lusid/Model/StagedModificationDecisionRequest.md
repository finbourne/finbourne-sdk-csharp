# Finbourne.Sdk.Lusid.Model.StagedModificationDecisionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Decision** | **string** | Required | The decision on the requested staged modification, can be &#39;Approve&#39; or &#39;Reject&#39;. |
| **Comment** | **string** | Required | Comment on decision. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationDecisionRequest(
    decision: "...",  // required — The decision on the requested staged modification, can be &#39;Approve&#39; or &#39;Reject&#39;.
    comment: "..."  // required — Comment on decision.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationDecisionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

