# Finbourne.Sdk.Lusid.Model.BlockAndOrdersCreateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;BlockAndOrdersRequest&gt;](BlockAndOrdersRequest.md) | Required | A collection of BlockAndOrdersRequest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BlockAndOrdersCreateRequest(
    requests: new List<BlockAndOrdersRequest>()  // required — A collection of BlockAndOrdersRequest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BlockAndOrdersCreateRequest>(json);
```


## Related Models

- [BlockAndOrdersRequest](BlockAndOrdersRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

