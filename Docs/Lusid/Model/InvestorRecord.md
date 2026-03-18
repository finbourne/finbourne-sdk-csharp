# Finbourne.Sdk.Lusid.Model.InvestorRecord

Representation of an Investor Record on the LUSID API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Optional | The scope in which the Investor Record lies. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Unique client-defined identifiers of the Investor Record. |
| **DisplayName** | **string** | Optional | The display name of the Investor Record |
| **Description** | **string** | Optional | The description of the Investor Record |
| **Investor** | [Investor](Investor.md) | Optional | *No description available.* |
| **LusidInvestorRecordId** | **string** | Optional | The unique LUSID Investor Record Identifier of the Investor Record. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Investor Record. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the Investor Record. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InvestorRecord(
    scope: "...",  // optional — The scope in which the Investor Record lies.
    identifiers: new Property(...),  // optional — Unique client-defined identifiers of the Investor Record.
    displayName: "...",  // optional — The display name of the Investor Record
    description: "...",  // optional — The description of the Investor Record
    investor: new Investor(...),  // optional
    lusidInvestorRecordId: "...",  // optional — The unique LUSID Investor Record Identifier of the Investor Record.
    properties: new Property(...),  // optional — A set of properties associated to the Investor Record.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the Investor Record.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InvestorRecord>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [Investor](Investor.md)
- [Property](Property.md) — used in `Properties`
- [Relationship](Relationship.md) — used in `Relationships`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

