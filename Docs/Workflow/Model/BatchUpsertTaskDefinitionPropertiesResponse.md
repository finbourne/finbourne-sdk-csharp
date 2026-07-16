# Finbourne.Sdk.Workflow.Model.BatchUpsertTaskDefinitionPropertiesResponse

The result of a batch upsert of properties on a Task Definition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties that were successfully upserted or deleted, keyed by property key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The properties that could not be upserted or deleted, keyed by property key. |
| **AsAtDate** | **DateTimeOffset** | Optional | The asAt datetime at which the properties were updated or created. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new BatchUpsertTaskDefinitionPropertiesResponse(
    values: new PerpetualProperty(...),  // optional — The properties that were successfully upserted or deleted, keyed by property key.
    failed: new ErrorDetail(...),  // optional — The properties that could not be upserted or deleted, keyed by property key.
    asAtDate: DateTimeOffset.Now,  // optional — The asAt datetime at which the properties were updated or created.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertTaskDefinitionPropertiesResponse>(json);
```


## Related Models

- [PerpetualProperty](PerpetualProperty.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

