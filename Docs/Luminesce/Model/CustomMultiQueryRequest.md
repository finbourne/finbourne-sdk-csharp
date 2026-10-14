# Finbourne.Sdk.Luminesce.Model.CustomMultiQueryRequest

A caller-supplied set of queries to run in the background, as one multi-query.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **string** | Optional | An explicit ExecutionId to use.  This must be blank OR assigned to a valid GUID-as-a-string. |
| **ScalarParameters** | **Dictionary&lt;string, string&gt;** | Optional | Scalar parameter values, handed to every query that runs (e.g. filling in &#x60;:someParameter:defaultValue&#x60; style references). At most 100, each named as an identifier of at most 256 characters, with a value of at most 4096. |
| **Queries** | [List&lt;CustomMultiQueryItem&gt;](CustomMultiQueryItem.md) | Required | The queries to run.  Those ready are started in the order given here (one still waiting on those it refers to does not hold up a later one), and each may only refer to queries earlier in the list. |
| **MaxInParallel** | **int?** | Optional | Maximum number of the queries that may run concurrently.  Defaults to 1, meaning they run one after another. Explicitly null means as many as their dependencies allow. |
| **TimeoutSeconds** | **int** | Optional | Maximum time each query may run for, in seconds, timed from when it starts: &lt;0 → ∞, 0 → 1200s (20m). There is no limit on the set as a whole. |
| **KeepForSeconds** | **int** | Optional | Maximum time the results may be kept for, in seconds: &lt;0 → 1200 (20m), 0 → 28800 (8h), max &#x3D; 2,678,400 (31d) |
| **QueryName** | **string** | Optional | A name for this set of queries.  This goes into logs and is returned when listing the sets of queries. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CustomMultiQueryRequest(
    executionId: "...",  // optional — An explicit ExecutionId to use.  This must be blank OR assigned to a valid GUID-as-a-string.
    scalarParameters: ,  // optional — Scalar parameter values, handed to every query that runs (e.g. filling in &#x60;:someParameter:defaultValue&#x60; style references). At most 100, each named as an identifier of at most 256 characters, with a value of at most 4096.
    queries: new List<CustomMultiQueryItem>(),  // required — The queries to run.  Those ready are started in the order given here (one still waiting on those it refers to does not hold up a later one), and each may only refer to queries earlier in the list.
    maxInParallel: 0,  // optional — Maximum number of the queries that may run concurrently.  Defaults to 1, meaning they run one after another. Explicitly null means as many as their dependencies allow.
    timeoutSeconds: 0,  // optional — Maximum time each query may run for, in seconds, timed from when it starts: &lt;0 → ∞, 0 → 1200s (20m). There is no limit on the set as a whole.
    keepForSeconds: 0,  // optional — Maximum time the results may be kept for, in seconds: &lt;0 → 1200 (20m), 0 → 28800 (8h), max &#x3D; 2,678,400 (31d)
    queryName: "..."  // optional — A name for this set of queries.  This goes into logs and is returned when listing the sets of queries.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomMultiQueryRequest>(json);
```

- [CustomMultiQueryItem](CustomMultiQueryItem.md) — used in `Queries`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

