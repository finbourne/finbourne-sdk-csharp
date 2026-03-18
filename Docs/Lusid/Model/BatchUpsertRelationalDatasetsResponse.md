# Finbourne.Sdk.Lusid.Model.BatchUpsertRelationalDatasetsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, RelationalDataPointResponse&gt;](RelationalDataPointResponse.md) | Required | A list of data points that were successfully upserted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A list of data points that failed to be upserted, along with the associated error message. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpsertRelationalDatasetsResponse(
    values: new RelationalDataPointResponse(...),  // required — A list of data points that were successfully upserted.
    failed: new ErrorDetail(...),  // optional — A list of data points that failed to be upserted, along with the associated error message.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertRelationalDatasetsResponse>(json);
```


## Related Models

- [RelationalDataPointResponse](RelationalDataPointResponse.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

