# Finbourne.Sdk.Lusid.Model.ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery

A version of the resource list for use with list endpoints that use the POST verb instead of GET, allowing  the endpoint to return the POST body(s) that can be sent in conjunction with the Next Page and/or Previous  Page links to retrieve the next/previous page of results. This should make it easier for SDK consumers to  fluently page through results. The PagedResourceList only exposes a page token string, typically for use in  a query parameter, and thus is more suited to GET endpoints.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;SettlementActivity&gt;](SettlementActivity.md) | Required | The resources to list. |
| **Href** | **string** | Optional | The URI of the resource list. |
| **PostBody** | [SettlementActivityQuery](SettlementActivityQuery.md) | Optional | *No description available.* |
| **NextPage** | [SettlementActivityQuery](SettlementActivityQuery.md) | Optional | *No description available.* |
| **PreviousPage** | [SettlementActivityQuery](SettlementActivityQuery.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery(
    values: new List<SettlementActivity>(),  // required — The resources to list.
    href: "...",  // optional — The URI of the resource list.
    postBody: new SettlementActivityQuery(...),  // optional
    nextPage: new SettlementActivityQuery(...),  // optional
    previousPage: new SettlementActivityQuery(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery>(json);
```


## Related Models

- [SettlementActivity](SettlementActivity.md) — used in `Values`
- [SettlementActivityQuery](SettlementActivityQuery.md)
- [SettlementActivityQuery](SettlementActivityQuery.md)
- [SettlementActivityQuery](SettlementActivityQuery.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

