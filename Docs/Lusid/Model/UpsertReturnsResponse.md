# Finbourne.Sdk.Lusid.Model.UpsertReturnsResponse

Response from upserting Returns
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | **List&lt;Dictionary&lt;string, DateTimeOffset&gt;&gt;** | Optional | The set of values that were successfully retrieved. |
| **Failed** | **List&lt;Dictionary&lt;string, ErrorDetail&gt;&gt;** | Optional | The set of values that could not be retrieved due along with a reason for this, e.g badly formed request. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertReturnsResponse(
    varVersion: new ModelVersion(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: ,  // optional — The set of values that were successfully retrieved.
    failed: ,  // optional — The set of values that could not be retrieved due along with a reason for this, e.g badly formed request.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertReturnsResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

