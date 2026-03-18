# Finbourne.Sdk.Lusid.Model.UpsertInstrumentsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, Instrument&gt;](Instrument.md) | Optional | The instruments which have been successfully updated or created. |
| **Staged** | [Dictionary&lt;string, Instrument&gt;](Instrument.md) | Optional | The instruments that have been staged for updation or creation. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The instruments that could not be updated or created or were left unchanged without error along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Meta data associated with the upsert event. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInstrumentsResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new Instrument(...),  // optional — The instruments which have been successfully updated or created.
    staged: new Instrument(...),  // optional — The instruments that have been staged for updation or creation.
    failed: new ErrorDetail(...),  // optional — The instruments that could not be updated or created or were left unchanged without error along with a reason for their failure.
    metadata: ,  // optional — Meta data associated with the upsert event.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInstrumentsResponse>(json);
```

- [Instrument](Instrument.md) — used in `Values`
- [Instrument](Instrument.md) — used in `Staged`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

