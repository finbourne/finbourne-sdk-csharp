# Finbourne.Sdk.Luminesce.Model.CustomMultiQueryListItemQuery

One of the queries of a Finbourne.Honeycomb.WebApi.BackgroundQueries.MultiQuery.CustomMultiQueryListItem
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The Name given to the query in the original request |
| **State** | **BackgroundQueryState** | Optional | *No description available.* |
| **HasResult** | **bool** | Optional | Whether its results may be fetched |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CustomMultiQueryListItemQuery(
    name: "...",  // optional — The Name given to the query in the original request
    state: ,  // optional
    hasResult: true  // optional — Whether its results may be fetched
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomMultiQueryListItemQuery>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

