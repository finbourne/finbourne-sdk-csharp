# Finbourne.Sdk.Lusid.Model.UpsertLegalEntityAccessMetadataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metadata** | [List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md) | Optional | The access control metadata to assign to a Legal Entity that matches the identifier |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertLegalEntityAccessMetadataRequest(
    metadata: new List<AccessMetadataValue>()  // optional — The access control metadata to assign to a Legal Entity that matches the identifier
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertLegalEntityAccessMetadataRequest>(json);
```


## Related Models

- [AccessMetadataValue](AccessMetadataValue.md) — used in `Metadata`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

