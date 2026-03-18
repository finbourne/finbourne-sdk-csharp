# Finbourne.Sdk.Lusid.Model.DeleteAccountsResponse

The delete accounts response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **AccountIds** | **List&lt;string&gt;** | Optional | The Accounts which have been soft/hard deleted. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteAccountsResponse(
    varVersion: new ModelVersion(...),  // optional
    accountIds: ,  // optional — The Accounts which have been soft/hard deleted.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteAccountsResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

