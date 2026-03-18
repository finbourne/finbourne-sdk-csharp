# Finbourne.Sdk.Lusid.Model.BlockSetRequest

A request to create or update multiple Blocks.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;BlockRequest&gt;](BlockRequest.md) | Optional | A collection of BlockRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BlockSetRequest(
    requests: new List<BlockRequest>()  // optional — A collection of BlockRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BlockSetRequest>(json);
```


## Related Models

- [BlockRequest](BlockRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

