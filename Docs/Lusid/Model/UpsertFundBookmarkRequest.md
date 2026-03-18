# Finbourne.Sdk.Lusid.Model.UpsertFundBookmarkRequest

A definition for the period you wish to close
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BookmarkCode** | **string** | Required | Unique code for the Bookmark. |
| **DisplayName** | **string** | Required | Identifiable Name assigned to the Bookmark. |
| **Description** | **string** | Optional | Description assigned to the Bookmark. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the Bookmark. |
| **QueryAsAt** | **DateTimeOffset?** | Optional | The query time of the Bookmark. Defaults to latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Bookmark. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Bookmark. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Bookmark. Defaults to Latest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertFundBookmarkRequest(
    bookmarkCode: "...",  // required — Unique code for the Bookmark.
    displayName: "...",  // required — Identifiable Name assigned to the Bookmark.
    description: "...",  // optional — Description assigned to the Bookmark.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the Bookmark.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the Bookmark. Defaults to latest.
    properties: new Property(...),  // optional — A set of properties for the Bookmark.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Bookmark. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now  // optional — The optional AsAt Override to use for performing valuations in the Bookmark. Defaults to Latest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertFundBookmarkRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

