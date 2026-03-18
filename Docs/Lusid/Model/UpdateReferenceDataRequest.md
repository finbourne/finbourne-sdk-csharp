# Finbourne.Sdk.Lusid.Model.UpdateReferenceDataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RequestDefinitions** | [List&lt;FieldDefinition&gt;](FieldDefinition.md) | Required | Definition of a reference data field. |
| **RequestValues** | [List&lt;FieldValue&gt;](FieldValue.md) | Required | Reference data. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateReferenceDataRequest(
    requestDefinitions: new List<FieldDefinition>(),  // required — Definition of a reference data field.
    requestValues: new List<FieldValue>()  // required — Reference data.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateReferenceDataRequest>(json);
```


## Related Models

- [FieldDefinition](FieldDefinition.md) — used in `RequestDefinitions`
- [FieldValue](FieldValue.md) — used in `RequestValues`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

