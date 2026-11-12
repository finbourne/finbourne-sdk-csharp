# Finbourne.Sdk.Luminesce.Model.DownloadQueryResultRequest

How to download the results of a background query: in what format, which of them, and (so far for csv, pipe and json only) formatted as the grid shows them.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Format** | **ExportType** | Optional | *No description available.* |
| **SortBy** | **string** | Optional | Order the results by these fields. Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;. Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;. Default is null, the sort order specified in the query itself. |
| **Filter** | **string** | Optional | Further limits the fetched results beyond that of the original query. - An ODATA filter per Finbourne.Filtering syntax, e.g. &#x60;SomeField eq &#39;Hello&#39;&#x60; - may be combined with &#x60;sqlFilter&#x60;. |
| **SqlFilter** | **string** | Optional | Further limits the fetched results beyond that of the original query. - Raw SQL for filtering, e.g. &#x60;strftime(&#39;%Y-%m&#39;, SomeDateField) &#x3D; &#39;2026-06&#39;&#x60; - may be combined with &#x60;filter&#x60; while supporting additional syntax that cannot. |
| **Select** | **string** | Optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited, and may aggregate the data, e.g. &#x60;some_field, count(*) as a, max(x) as b&#x60; (where &#x60;groupBy&#x60; would likely be &#x60;1&#x60;). The columns of &#x60;formatting&#x60; are in terms of the columns selected. |
| **GroupBy** | **string** | Optional | Groups by the specified fields: a comma delimited list of 1 based numeric indexes into &#x60;select&#x60;, or repeats of its expressions. Default is null (meaning no grouping will be performed on the selected columns). |
| **DateTimeFormat** | **string** | Optional | Format to apply for DateTime data not otherwise formatted, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **LoadWaitMilliseconds** | **int** | Optional | Optional maximum additional wait period for post execution platform processing. |
| **Formatting** | [ExportFormatting](ExportFormatting.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new DownloadQueryResultRequest(
    format: ,  // optional
    sortBy: "...",  // optional — Order the results by these fields. Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;. Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;. Default is null, the sort order specified in the query itself.
    filter: "...",  // optional — Further limits the fetched results beyond that of the original query. - An ODATA filter per Finbourne.Filtering syntax, e.g. &#x60;SomeField eq &#39;Hello&#39;&#x60; - may be combined with &#x60;sqlFilter&#x60;.
    sqlFilter: "...",  // optional — Further limits the fetched results beyond that of the original query. - Raw SQL for filtering, e.g. &#x60;strftime(&#39;%Y-%m&#39;, SomeDateField) &#x3D; &#39;2026-06&#39;&#x60; - may be combined with &#x60;filter&#x60; while supporting additional syntax that cannot.
    select: "...",  // optional — Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited, and may aggregate the data, e.g. &#x60;some_field, count(*) as a, max(x) as b&#x60; (where &#x60;groupBy&#x60; would likely be &#x60;1&#x60;). The columns of &#x60;formatting&#x60; are in terms of the columns selected.
    groupBy: "...",  // optional — Groups by the specified fields: a comma delimited list of 1 based numeric indexes into &#x60;select&#x60;, or repeats of its expressions. Default is null (meaning no grouping will be performed on the selected columns).
    dateTimeFormat: "...",  // optional — Format to apply for DateTime data not otherwise formatted, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60;
    loadWaitMilliseconds: 0,  // optional — Optional maximum additional wait period for post execution platform processing.
    formatting: new ExportFormatting(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DownloadQueryResultRequest>(json);
```

- [ExportFormatting](ExportFormatting.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

