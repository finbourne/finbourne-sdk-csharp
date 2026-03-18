# Finbourne.Sdk.Lusid.Model.BatchUpsertPropertyDefinitionPropertiesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | The properties that have been successfully upserted |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Required | The properties that could not be upserted along with a reason for their failure. |
| **AsAtDate** | **DateTimeOffset** | Required | The as-at datetime at which properties were created or updated. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpsertPropertyDefinitionPropertiesResponse(
    values: new Property(...),  // required — The properties that have been successfully upserted
    failed: new ErrorDetail(...),  // required — The properties that could not be upserted along with a reason for their failure.
    asAtDate: DateTimeOffset.Now,  // required — The as-at datetime at which properties were created or updated.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertPropertyDefinitionPropertiesResponse>(json);
```


## Related Models

- [Property](Property.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

