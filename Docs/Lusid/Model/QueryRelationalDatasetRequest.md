# Finbourne.Sdk.Lusid.Model.QueryRelationalDatasetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **QueryMethod** | **string** | Optional | The method used to query data points. Can be either &#39;Latest&#39; or &#39;TimeSeries&#39;. |
| **Filter** | **string** | Optional | Expression to filter the result set. For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **CustomSortBy** | [List&lt;CustomSortBy&gt;](CustomSortBy.md) | Optional | A list of fields and values to sort the results by. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryRelationalDatasetRequest(
    queryMethod: "...",  // optional — The method used to query data points. Can be either &#39;Latest&#39; or &#39;TimeSeries&#39;.
    filter: "...",  // optional — Expression to filter the result set. For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914.
    customSortBy: new List<CustomSortBy>()  // optional — A list of fields and values to sort the results by.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryRelationalDatasetRequest>(json);
```

- [CustomSortBy](CustomSortBy.md) — used in `CustomSortBy`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

