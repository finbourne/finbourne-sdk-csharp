# Finbourne.Sdk.Luminesce.Model.CustomMultiQueryListItem

A custom multi-query the calling user currently has results of available to them
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **string** | Optional | ExecutionId of the multi-query, its queries having ExecutionIds of &#x60;{ExecutionId}_{Name}&#x60; |
| **QueryName** | **string** | Optional | The QueryName given in the original request |
| **State** | **BackgroundQueryState** | Optional | *No description available.* |
| **StartedAt** | **DateTimeOffset?** | Optional | When it was started (UTC) |
| **When** | **DateTimeOffset** | Optional | When the state of it was last updated (UTC) |
| **ExpiresAt** | **DateTimeOffset** | Optional | When it (and the data of its queries) may be removed (UTC) |
| **Queries** | [List&lt;CustomMultiQueryListItemQuery&gt;](CustomMultiQueryListItemQuery.md) | Optional | Its queries whose results may be fetched (those that are external results), in request order |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CustomMultiQueryListItem(
    executionId: "...",  // optional — ExecutionId of the multi-query, its queries having ExecutionIds of &#x60;{ExecutionId}_{Name}&#x60;
    queryName: "...",  // optional — The QueryName given in the original request
    state: ,  // optional
    startedAt: DateTimeOffset.Now,  // optional — When it was started (UTC)
    when: DateTimeOffset.Now,  // optional — When the state of it was last updated (UTC)
    expiresAt: DateTimeOffset.Now,  // optional — When it (and the data of its queries) may be removed (UTC)
    queries: new List<CustomMultiQueryListItemQuery>()  // optional — Its queries whose results may be fetched (those that are external results), in request order
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomMultiQueryListItem>(json);
```

- [CustomMultiQueryListItemQuery](CustomMultiQueryListItemQuery.md) — used in `Queries`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

