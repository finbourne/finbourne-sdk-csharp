# Finbourne.Sdk.Lusid.Model.CreatePortfolioGroupRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code that the portfolio group will be created with. Together with the scope this uniquely identifies the portfolio group. |
| **Created** | **DateTimeOffset?** | Optional | The effective datetime at which the portfolio group was created. Defaults to the current LUSID system datetime if not specified. |
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The resource identifiers of the portfolios to be contained within the portfolio group. |
| **SubGroups** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The resource identifiers of the portfolio groups to be contained within the portfolio group as sub groups. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of unique group properties to add to the portfolio group. Each property must be from the &#39;PortfolioGroup&#39; domain and should be identified by its key which has the format {domain}/{scope}/{code}, e.g. &#39;PortfolioGroup/Manager/Id&#39;. These properties must be pre-defined. |
| **DisplayName** | **string** | Required | The name of the portfolio group. |
| **Description** | **string** | Optional | A long form description of the portfolio group. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreatePortfolioGroupRequest(
    code: "...",  // required — The code that the portfolio group will be created with. Together with the scope this uniquely identifies the portfolio group.
    created: DateTimeOffset.Now,  // optional — The effective datetime at which the portfolio group was created. Defaults to the current LUSID system datetime if not specified.
    values: new List<ResourceId>(),  // optional — The resource identifiers of the portfolios to be contained within the portfolio group.
    subGroups: new List<ResourceId>(),  // optional — The resource identifiers of the portfolio groups to be contained within the portfolio group as sub groups.
    properties: new Property(...),  // optional — A set of unique group properties to add to the portfolio group. Each property must be from the &#39;PortfolioGroup&#39; domain and should be identified by its key which has the format {domain}/{scope}/{code}, e.g. &#39;PortfolioGroup/Manager/Id&#39;. These properties must be pre-defined.
    displayName: "...",  // required — The name of the portfolio group.
    description: "..."  // optional — A long form description of the portfolio group.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreatePortfolioGroupRequest>(json);
```

- [ResourceId](ResourceId.md) — used in `Values`
- [ResourceId](ResourceId.md) — used in `SubGroups`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

