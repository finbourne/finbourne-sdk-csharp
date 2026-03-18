# Finbourne.Sdk.Lusid.Model.UpsertCustomEntitiesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, CustomEntityResponse&gt;](CustomEntityResponse.md) | Optional | The custom-entities which have been successfully updated or created. |
| **Staged** | [Dictionary&lt;string, CustomEntityResponse&gt;](CustomEntityResponse.md) | Optional | The custom-entities that have been staged for update or creation. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The custom-entities that could not be updated or created or were left unchanged without error along with a reason for their failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCustomEntitiesResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new CustomEntityResponse(...),  // optional — The custom-entities which have been successfully updated or created.
    staged: new CustomEntityResponse(...),  // optional — The custom-entities that have been staged for update or creation.
    failed: new ErrorDetail(...),  // optional — The custom-entities that could not be updated or created or were left unchanged without error along with a reason for their failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCustomEntitiesResponse>(json);
```

- [CustomEntityResponse](CustomEntityResponse.md) — used in `Values`
- [CustomEntityResponse](CustomEntityResponse.md) — used in `Staged`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

