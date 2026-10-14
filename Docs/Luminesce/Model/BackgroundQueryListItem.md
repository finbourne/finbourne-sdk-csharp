# Finbourne.Sdk.Luminesce.Model.BackgroundQueryListItem

A background query the calling user currently has available to them
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **string** | Optional | ExecutionId of the query |
| **Query** | **string** | Optional | The LuminesceSql of the original request |
| **QueryName** | **string** | Optional | The QueryName given in the original request |
| **State** | **BackgroundQueryState** | Optional | *No description available.* |
| **When** | **DateTimeOffset** | Optional | When the state of this query (and so its data) was last updated (UTC) |
| **ExpiresAt** | **DateTimeOffset** | Optional | When the query (and its data) may be removed (UTC) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundQueryListItem(
    executionId: "...",  // optional — ExecutionId of the query
    query: "...",  // optional — The LuminesceSql of the original request
    queryName: "...",  // optional — The QueryName given in the original request
    state: ,  // optional
    when: DateTimeOffset.Now,  // optional — When the state of this query (and so its data) was last updated (UTC)
    expiresAt: DateTimeOffset.Now  // optional — When the query (and its data) may be removed (UTC)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundQueryListItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

