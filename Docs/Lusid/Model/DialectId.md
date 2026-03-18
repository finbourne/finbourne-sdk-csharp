# Finbourne.Sdk.Lusid.Model.DialectId

Unique identifier of a given Dialect
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The Scope of the dialect. |
| **Vendor** | **string** | Required | The vendor of the dialect, the entity that created it. e.g. ISDA, FINBOURNE. |
| **SourceSystem** | **string** | Required | The source system of the dialect, the system that understands it. e.g. LUSID, QuantLib. |
| **VarVersion** | **string** | Required | The semantic version of the dialect: MAJOR.MINOR.PATCH. |
| **SerialisationFormat** | **string** | Required | The serialisation format of a document in this dialect. e.g. JSON, XML. |
| **EntityType** | **string** | Required | The type of entity this dialect describes e.g. Instrument. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DialectId(
    scope: "...",  // required — The Scope of the dialect.
    vendor: "...",  // required — The vendor of the dialect, the entity that created it. e.g. ISDA, FINBOURNE.
    sourceSystem: "...",  // required — The source system of the dialect, the system that understands it. e.g. LUSID, QuantLib.
    varVersion: "...",  // required — The semantic version of the dialect: MAJOR.MINOR.PATCH.
    serialisationFormat: "...",  // required — The serialisation format of a document in this dialect. e.g. JSON, XML.
    entityType: "..."  // required — The type of entity this dialect describes e.g. Instrument.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DialectId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

