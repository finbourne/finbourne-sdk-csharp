# Finbourne.Sdk.Lusid.Model.BatchDeleteRelationalDataResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | **Dictionary&lt;string, string&gt;** | Required | A list of data points that were successfully upserted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A list of data points that failed to be upserted, along with the associated error message. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchDeleteRelationalDataResponse(
    values: ,  // required — A list of data points that were successfully upserted.
    failed: new ErrorDetail(...),  // optional — A list of data points that failed to be upserted, along with the associated error message.
    href: "..."  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchDeleteRelationalDataResponse>(json);
```

- [ErrorDetail](ErrorDetail.md) — used in `Failed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

