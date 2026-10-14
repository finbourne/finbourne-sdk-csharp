# Finbourne.Sdk.Lusid.Model.StructuredResultDataResult

Represents structured result data document and row details for a data quality check result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Optional | The type of the entity, e.g. \&quot;SrsRow\&quot;. |
| **AsAt** | **DateTimeOffset** | Optional | The as-at timestamp the document was read at |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective-at timestamp the document was read at |
| **DocumentEffectiveAt** | **DateTimeOffset** | Optional | The effective date of the upload the row was read from: the latest upload at or before effectiveAt |
| **Scope** | **string** | Optional | The scope of the document |
| **Code** | **string** | Optional | The code of the document |
| **Source** | **string** | Optional | The platform or vendor that provided the document |
| **ResultType** | **string** | Optional | The document&#39;s result type |
| **RowIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | The row&#39;s identifier columns, keyed by address key. Populated when entityType is \&quot;SrsRow\&quot;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StructuredResultDataResult(
    entityType: "...",  // optional — The type of the entity, e.g. \&quot;SrsRow\&quot;.
    asAt: DateTimeOffset.Now,  // optional — The as-at timestamp the document was read at
    effectiveAt: DateTimeOffset.Now,  // optional — The effective-at timestamp the document was read at
    documentEffectiveAt: DateTimeOffset.Now,  // optional — The effective date of the upload the row was read from: the latest upload at or before effectiveAt
    scope: "...",  // optional — The scope of the document
    code: "...",  // optional — The code of the document
    source: "...",  // optional — The platform or vendor that provided the document
    resultType: "...",  // optional — The document&#39;s result type
    rowIdentifiers:   // optional — The row&#39;s identifier columns, keyed by address key. Populated when entityType is \&quot;SrsRow\&quot;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StructuredResultDataResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

