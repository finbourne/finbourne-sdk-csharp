# Finbourne.Sdk.Lusid.Model.MarginRunIssue

Something a margin run could not do for some of its agreements, and why.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Agreements** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The collateral agreements the issue concerns. |
| **Detail** | **string** | Required | What prevented the agreements from being valued. |
| **ShardId** | **string** | Optional | The shard the issue arose in, when it arose while valuing. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunIssue(
    agreements: new List<ResourceId>(),  // required — The collateral agreements the issue concerns.
    detail: "...",  // required — What prevented the agreements from being valued.
    shardId: "..."  // optional — The shard the issue arose in, when it arose while valuing.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRunIssue>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `Agreements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

