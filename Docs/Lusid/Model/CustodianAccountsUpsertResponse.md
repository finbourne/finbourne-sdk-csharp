# Finbourne.Sdk.Lusid.Model.CustodianAccountsUpsertResponse

The upsert accounts response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **CustodianAccounts** | [List&lt;CustodianAccount&gt;](CustodianAccount.md) | Optional | The Custodian Accounts which have been upserted. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustodianAccountsUpsertResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    custodianAccounts: new List<CustodianAccount>(),  // optional — The Custodian Accounts which have been upserted.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustodianAccountsUpsertResponse>(json);
```

- [ModelVersion](ModelVersion.md)
- [CustodianAccount](CustodianAccount.md) — used in `CustodianAccounts`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

