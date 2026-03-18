# Finbourne.Sdk.Luminesce.Model.BackgroundQueryResponse

Response for Background Query Start requests
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **string** | Optional | ExecutionId of the started-query |
| **Progress** | [Link](Link.md) | Optional | *No description available.* |
| **Cancel** | [Link](Link.md) | Optional | *No description available.* |
| **FetchJson** | [Link](Link.md) | Optional | *No description available.* |
| **FetchJsonProper** | [Link](Link.md) | Optional | *No description available.* |
| **FetchJsonProperWithLineage** | [Link](Link.md) | Optional | *No description available.* |
| **FetchXml** | [Link](Link.md) | Optional | *No description available.* |
| **FetchParquet** | [Link](Link.md) | Optional | *No description available.* |
| **FetchCsv** | [Link](Link.md) | Optional | *No description available.* |
| **FetchPipe** | [Link](Link.md) | Optional | *No description available.* |
| **FetchExcel** | [Link](Link.md) | Optional | *No description available.* |
| **FetchSqlite** | [Link](Link.md) | Optional | *No description available.* |
| **Histogram** | [Link](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundQueryResponse(
    executionId: "...",  // optional — ExecutionId of the started-query
    progress: new Link(...),  // optional
    cancel: new Link(...),  // optional
    fetchJson: new Link(...),  // optional
    fetchJsonProper: new Link(...),  // optional
    fetchJsonProperWithLineage: new Link(...),  // optional
    fetchXml: new Link(...),  // optional
    fetchParquet: new Link(...),  // optional
    fetchCsv: new Link(...),  // optional
    fetchPipe: new Link(...),  // optional
    fetchExcel: new Link(...),  // optional
    fetchSqlite: new Link(...),  // optional
    histogram: new Link(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundQueryResponse>(json);
```

- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

