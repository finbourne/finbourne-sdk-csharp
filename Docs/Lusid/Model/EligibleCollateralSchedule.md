# Finbourne.Sdk.Lusid.Model.EligibleCollateralSchedule

An eligible collateral schedule: the collateral a party may post under a margin arrangement and the valuation  percentage each class of collateral is accepted at.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Optional | A description of the Eligible Collateral Schedule. Optional. |
| **Rows** | [List&lt;EligibleCollateralRow&gt;](EligibleCollateralRow.md) | Optional | The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Eligible Collateral Schedule. Filterable. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibleCollateralSchedule(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    description: "...",  // optional — A description of the Eligible Collateral Schedule. Optional.
    rows: new List<EligibleCollateralRow>(),  // optional — The classes of collateral that may be posted, each with the valuation percentage it is accepted at. At least one and at most 200 rows.
    varVersion: new ModelVersion(...),  // optional
    properties: new Property(...),  // optional — A set of properties to decorate onto the Eligible Collateral Schedule. Filterable.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibleCollateralSchedule>(json);
```

- [ResourceId](ResourceId.md)
- [EligibleCollateralRow](EligibleCollateralRow.md) — used in `Rows`
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

