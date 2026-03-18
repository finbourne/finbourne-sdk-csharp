# Finbourne.Sdk.Luminesce.Model.BackgroundMultiQueryResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **Guid** | Optional | *No description available.* *(read-only)* |
| **Progress** | [Link](Link.md) | Optional | *No description available.* |
| **Cancel** | [Link](Link.md) | Optional | *No description available.* |
| **FetchJson** | [List&lt;Link&gt;](Link.md) | Optional | Json (as a string) data request links for all of the child queries *(read-only)* |
| **FetchJsonProper** | [List&lt;Link&gt;](Link.md) | Optional | Json-proper data request links for all of the child queries *(read-only)* |
| **FetchJsonProperWithLineage** | [List&lt;Link&gt;](Link.md) | Optional | Json-proper-with-lineage data request links for all of the child queries *(read-only)* |
| **FetchXml** | [List&lt;Link&gt;](Link.md) | Optional | Xml data request links for all of the child queries *(read-only)* |
| **FetchParquet** | [List&lt;Link&gt;](Link.md) | Optional | Parquet data request links for all of the child queries *(read-only)* |
| **FetchCsv** | [List&lt;Link&gt;](Link.md) | Optional | CSV data request links for all of the child queries *(read-only)* |
| **FetchPipe** | [List&lt;Link&gt;](Link.md) | Optional | Pipe delimited data request links for all of the child queries *(read-only)* |
| **FetchExcel** | [List&lt;Link&gt;](Link.md) | Optional | Excel workbook data request links for all of the child queries *(read-only)* |
| **FetchSqlite** | [List&lt;Link&gt;](Link.md) | Optional | SqLite DB data request links for all of the child queries *(read-only)* |
| **Histogram** | [List&lt;Link&gt;](Link.md) | Optional | Histogram links for all of the child queries *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundMultiQueryResponse(
    executionId: "...",  // optional
    progress: new Link(...),  // optional
    cancel: new Link(...),  // optional
    fetchJson: new List<Link>(),  // optional — Json (as a string) data request links for all of the child queries
    fetchJsonProper: new List<Link>(),  // optional — Json-proper data request links for all of the child queries
    fetchJsonProperWithLineage: new List<Link>(),  // optional — Json-proper-with-lineage data request links for all of the child queries
    fetchXml: new List<Link>(),  // optional — Xml data request links for all of the child queries
    fetchParquet: new List<Link>(),  // optional — Parquet data request links for all of the child queries
    fetchCsv: new List<Link>(),  // optional — CSV data request links for all of the child queries
    fetchPipe: new List<Link>(),  // optional — Pipe delimited data request links for all of the child queries
    fetchExcel: new List<Link>(),  // optional — Excel workbook data request links for all of the child queries
    fetchSqlite: new List<Link>(),  // optional — SqLite DB data request links for all of the child queries
    histogram: new List<Link>()  // optional — Histogram links for all of the child queries
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundMultiQueryResponse>(json);
```

- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md) — used in `FetchJson`
- [Link](Link.md) — used in `FetchJsonProper`
- [Link](Link.md) — used in `FetchJsonProperWithLineage`
- [Link](Link.md) — used in `FetchXml`
- [Link](Link.md) — used in `FetchParquet`
- [Link](Link.md) — used in `FetchCsv`
- [Link](Link.md) — used in `FetchPipe`
- [Link](Link.md) — used in `FetchExcel`
- [Link](Link.md) — used in `FetchSqlite`
- [Link](Link.md) — used in `Histogram`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

