# Finbourne.Sdk.Lusid.Model.StagedModificationDecision

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Optional | Time the decision request is made. |
| **UserId** | **string** | Optional | ID of user that approved the request. |
| **RequestId** | **string** | Optional | ID of user that made the request. |
| **Decision** | **string** | Optional | The decision on the requested staged modification, can be &#39;Approve&#39; or &#39;Reject&#39;. |
| **Comment** | **string** | Optional | Comment on decision. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationDecision(
    asAt: DateTimeOffset.Now,  // optional — Time the decision request is made.
    userId: "...",  // optional — ID of user that approved the request.
    requestId: "...",  // optional — ID of user that made the request.
    decision: "...",  // optional — The decision on the requested staged modification, can be &#39;Approve&#39; or &#39;Reject&#39;.
    comment: "..."  // optional — Comment on decision.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationDecision>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

