# Finbourne.Sdk.Lusid.Model.VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Values** | [List&lt;SettlementInstructionWithTransaction&gt;](SettlementInstructionWithTransaction.md) | Required | The resources to list. |
| **Href** | **string** | Optional | The URI of the resource list. |
| **PostBody** | [SettlementInstructionQuery](SettlementInstructionQuery.md) | Optional | *No description available.* |
| **NextPage** | [SettlementInstructionQuery](SettlementInstructionQuery.md) | Optional | *No description available.* |
| **PreviousPage** | [SettlementInstructionQuery](SettlementInstructionQuery.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery(
    varVersion: new ModelVersion(...),  // required
    values: new List<SettlementInstructionWithTransaction>(),  // required — The resources to list.
    href: "...",  // optional — The URI of the resource list.
    postBody: new SettlementInstructionQuery(...),  // optional
    nextPage: new SettlementInstructionQuery(...),  // optional
    previousPage: new SettlementInstructionQuery(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [SettlementInstructionWithTransaction](SettlementInstructionWithTransaction.md) — used in `Values`
- [SettlementInstructionQuery](SettlementInstructionQuery.md)
- [SettlementInstructionQuery](SettlementInstructionQuery.md)
- [SettlementInstructionQuery](SettlementInstructionQuery.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

