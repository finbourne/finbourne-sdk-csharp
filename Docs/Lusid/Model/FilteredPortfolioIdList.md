# Finbourne.Sdk.Lusid.Model.FilteredPortfolioIdList

> **Inherits from:** [ReferenceList](ReferenceList.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Filter** | **string** | Required | The filter that selects the portfolios in the list. It is stored as given and resolved against the portfolios the caller is entitled to see each time the list is read. Supports portfolio fields (e.g. id.scope, displayName, type) and portfolio properties (e.g. properties[Portfolio/MyScope/Strategy] eq &#39;Equity&#39;). Relationship filters are not supported. Time-variant properties are evaluated at the asAt of the request; there is no effectiveAt. On upsert the filter must resolve successfully. |
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The ids of the portfolios the filter resolved to when the list was read. Read only; must not be supplied on upsert. *(read-only)* |
| **ReferenceListType** | **string** | Required | The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList, FilteredPortfolioIdList. Default: `ReferenceListTypeEnum.FilteredPortfolioIdList` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FilteredPortfolioIdList(
    filter: "...",  // required — The filter that selects the portfolios in the list. It is stored as given and resolved against the portfolios the caller is entitled to see each time the list is read. Supports portfolio fields (e.g. id.scope, displayName, type) and portfolio properties (e.g. properties[Portfolio/MyScope/Strategy] eq &#39;Equity&#39;). Relationship filters are not supported. Time-variant properties are evaluated at the asAt of the request; there is no effectiveAt. On upsert the filter must resolve successfully.
    values: new List<ResourceId>(),  // optional — The ids of the portfolios the filter resolved to when the list was read. Read only; must not be supplied on upsert.
    referenceListType: "..."  // required — The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList, FilteredPortfolioIdList.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FilteredPortfolioIdList>(json);
```


- [ResourceId](ResourceId.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

