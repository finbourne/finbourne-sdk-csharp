# Finbourne.Sdk.Lusid.Model.UpsertInstrumentEventsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, InstrumentEventHolder&gt;](InstrumentEventHolder.md) | Optional | The corporate actions which have been successfully updated or inserted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The corporate actions that could not be updated or inserted along with a reason for their failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInstrumentEventsResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new InstrumentEventHolder(...),  // optional — The corporate actions which have been successfully updated or inserted.
    failed: new ErrorDetail(...),  // optional — The corporate actions that could not be updated or inserted along with a reason for their failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInstrumentEventsResponse>(json);
```

- [InstrumentEventHolder](InstrumentEventHolder.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

