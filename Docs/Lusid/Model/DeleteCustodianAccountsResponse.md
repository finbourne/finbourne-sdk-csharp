# Finbourne.Sdk.Lusid.Model.DeleteCustodianAccountsResponse

The delete custodian accounts response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **CustodianAccountIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The Custodian Accounts which have been soft/hard deleted. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteCustodianAccountsResponse(
    varVersion: new ModelVersion(...),  // optional
    custodianAccountIds: new List<ResourceId>(),  // optional — The Custodian Accounts which have been soft/hard deleted.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteCustodianAccountsResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md) — used in `CustodianAccountIds`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

