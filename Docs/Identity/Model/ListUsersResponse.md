# Finbourne.Sdk.Identity.Model.ListUsersResponse

Users directory query response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | Uri of this response |
| **Values** | [Dictionary&lt;string, UserSummary&gt;](UserSummary.md) | Optional | Successful entities, indexed by their id |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | Failed entities, indexed by their id |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ListUsersResponse(
    href: "...",  // optional — Uri of this response
    values: new UserSummary(...),  // optional — Successful entities, indexed by their id
    failed: new ErrorDetail(...),  // optional — Failed entities, indexed by their id
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ListUsersResponse>(json);
```

- [UserSummary](UserSummary.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

