# Finbourne.Sdk.Luminesce.Model.CustomMultiQueryItem

One query within a Finbourne.Honeycomb.WebApi.BackgroundQueries.MultiQuery.CustomMultiQueryRequest, given as either raw LuminesceSql or a saved query reference.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Unique name of the query, of at most 31 characters. Later queries refer to this one&#39;s results as &#x60;@Name&#x60;, and it names the result in any export. |
| **Sql** | **string** | Optional | The LuminesceSql to run.  Exactly one of this and &#x60;SavedQuery&#x60; must be given. |
| **SavedQuery** | **string** | Optional | A key within the Saved Queries (of the Workspaces API) to load the SQL from.  Exactly one of this and &#x60;Sql&#x60; must be given. e.g. &#x60;personal/YourUserId/items/queries/SomeQuery&#x60; or &#x60;shared/SomeWorkspace/items/queries/SomeQuery&#x60;. |
| **IsExternalResult** | **bool** | Optional | Should the results of this query be fetchable / exported?  If false it is only an intermediate step for later queries. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CustomMultiQueryItem(
    name: "...",  // required — Unique name of the query, of at most 31 characters. Later queries refer to this one&#39;s results as &#x60;@Name&#x60;, and it names the result in any export.
    sql: "...",  // optional — The LuminesceSql to run.  Exactly one of this and &#x60;SavedQuery&#x60; must be given.
    savedQuery: "...",  // optional — A key within the Saved Queries (of the Workspaces API) to load the SQL from.  Exactly one of this and &#x60;Sql&#x60; must be given. e.g. &#x60;personal/YourUserId/items/queries/SomeQuery&#x60; or &#x60;shared/SomeWorkspace/items/queries/SomeQuery&#x60;.
    isExternalResult: true  // optional — Should the results of this query be fetchable / exported?  If false it is only an intermediate step for later queries.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomMultiQueryItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

