# Finbourne.Sdk.Lusid.Model.BatchManageCommentRequest

One item of a batch comment request. The operation (add/edit/delete) is inferred from the  combination of commentId and commentText.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceId** | [RecInstanceId](RecInstanceId.md) | Required | *No description available.* |
| **RecType** | **string** | Required | The rec type whose results this item targets (e.g. Holding). Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External. |
| **RunNumber** | **int** | Required | The run of the instance whose results this item targets. |
| **RecResultId** | **string** | Required | The rec result the comment operation targets. |
| **CommentId** | **string** | Optional | The comment id. Null with text &#x3D; add; provided with text &#x3D; edit; provided with null text &#x3D; delete. |
| **CommentText** | **string** | Optional | The comment body. See operation inference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchManageCommentRequest(
    instanceId: new RecInstanceId(...),  // required
    recType: "...",  // required — The rec type whose results this item targets (e.g. Holding). Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External.
    runNumber: 0,  // required — The run of the instance whose results this item targets.
    recResultId: "...",  // required — The rec result the comment operation targets.
    commentId: "...",  // optional — The comment id. Null with text &#x3D; add; provided with text &#x3D; edit; provided with null text &#x3D; delete.
    commentText: "..."  // optional — The comment body. See operation inference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchManageCommentRequest>(json);
```


## Related Models

- [RecInstanceId](RecInstanceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

