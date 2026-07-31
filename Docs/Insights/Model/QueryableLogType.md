# Finbourne.Sdk.Insights.Model.QueryableLogType

The queryable fields of a single log type, returned by the queryable-fields metadata endpoint.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LogType** | **string** | Required | The log type, e.g. Requests, Vendor, Access, Trace or TraceEvent. |
| **Fields** | [List&lt;QueryableLogField&gt;](QueryableLogField.md) | Required | The fields of this log type that can be selected and/or filtered. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new QueryableLogType(
    logType: "...",  // required — The log type, e.g. Requests, Vendor, Access, Trace or TraceEvent.
    fields: new List<QueryableLogField>()  // required — The fields of this log type that can be selected and/or filtered.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryableLogType>(json);
```

- [QueryableLogField](QueryableLogField.md) — used in `Fields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

