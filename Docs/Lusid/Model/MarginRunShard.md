# Finbourne.Sdk.Lusid.Model.MarginRunShard

One valuation shard of a margin run: the agreements it values with one recipe, and how far it has got.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The identifier of the shard within the run. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Agreements** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The collateral agreements the shard values. |
| **Status** | **string** | Required | The status of the shard. One of Pending, Running, Completed or Failed. |
| **CallCount** | **int** | Required | The number of margin calls the shard published. |
| **LineCount** | **int** | Required | The number of margin lines the shard published. |
| **Detail** | **string** | Optional | Why the shard failed, when it did. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunShard(
    id: "...",  // required — The identifier of the shard within the run.
    recipeId: new ResourceId(...),  // optional
    agreements: new List<ResourceId>(),  // required — The collateral agreements the shard values.
    status: "...",  // required — The status of the shard. One of Pending, Running, Completed or Failed.
    callCount: 0,  // required — The number of margin calls the shard published.
    lineCount: 0,  // required — The number of margin lines the shard published.
    detail: "..."  // optional — Why the shard failed, when it did.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRunShard>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `Agreements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

