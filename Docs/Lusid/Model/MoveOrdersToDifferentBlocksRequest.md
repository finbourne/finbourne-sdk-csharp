# Finbourne.Sdk.Lusid.Model.MoveOrdersToDifferentBlocksRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;BlockAndOrderIdRequest&gt;](BlockAndOrderIdRequest.md) | Required | A collection of BlockAndOrderId. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MoveOrdersToDifferentBlocksRequest(
    requests: new List<BlockAndOrderIdRequest>()  // required — A collection of BlockAndOrderId.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MoveOrdersToDifferentBlocksRequest>(json);
```


## Related Models

- [BlockAndOrderIdRequest](BlockAndOrderIdRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

