# Finbourne.Sdk.Lusid.Model.CurrencyGroupResponse

A currency group: a set of related currencies sharing a major unit (e.g. GBP with minor unit GBX at 100:1).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The code of the currency group. This uniquely identifies the currency group within the tenant. |
| **DisplayName** | **string** | Optional | The name of the currency group. |
| **Description** | **string** | Optional | A description for the currency group. |
| **MajorUnitCurrency** | **string** | Optional | The three to five letter, case-sensitive currency code of the group&#39;s major unit, e.g. GBP for the sterling group. |
| **CirculationDomain** | **List&lt;string&gt;** | Optional | The domains in which the group&#39;s currencies circulate, e.g. ISO 3166 country codes or the ISO 4217 entity names of the countries using the major unit. |
| **MinorUnits** | [List&lt;CurrencyGroupMinorUnit&gt;](CurrencyGroupMinorUnit.md) | Optional | The minor unit currencies belonging to this currency group. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CurrencyGroupResponse(
    code: "...",  // optional — The code of the currency group. This uniquely identifies the currency group within the tenant.
    displayName: "...",  // optional — The name of the currency group.
    description: "...",  // optional — A description for the currency group.
    majorUnitCurrency: "...",  // optional — The three to five letter, case-sensitive currency code of the group&#39;s major unit, e.g. GBP for the sterling group.
    circulationDomain: ,  // optional — The domains in which the group&#39;s currencies circulate, e.g. ISO 3166 country codes or the ISO 4217 entity names of the countries using the major unit.
    minorUnits: new List<CurrencyGroupMinorUnit>(),  // optional — The minor unit currencies belonging to this currency group.
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CurrencyGroupResponse>(json);
```

- [CurrencyGroupMinorUnit](CurrencyGroupMinorUnit.md) — used in `MinorUnits`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

