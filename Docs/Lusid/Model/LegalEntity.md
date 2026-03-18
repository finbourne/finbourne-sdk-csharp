# Finbourne.Sdk.Lusid.Model.LegalEntity

Representation of Legal Entity on LUSID API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the Legal Entity |
| **Description** | **string** | Optional | The description of the Legal Entity |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **LusidLegalEntityId** | **string** | Optional | The unique LUSID Legal Entity Identifier of the Legal Entity. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Unique client-defined identifiers of the Legal Entity. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Legal Entity. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the Legal Entity. |
| **CounterpartyRiskInformation** | [CounterpartyRiskInformation](CounterpartyRiskInformation.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LegalEntity(
    displayName: "...",  // optional — The display name of the Legal Entity
    description: "...",  // optional — The description of the Legal Entity
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    lusidLegalEntityId: "...",  // optional — The unique LUSID Legal Entity Identifier of the Legal Entity.
    identifiers: new Property(...),  // optional — Unique client-defined identifiers of the Legal Entity.
    properties: new Property(...),  // optional — A set of properties associated to the Legal Entity.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the Legal Entity.
    counterpartyRiskInformation: new CounterpartyRiskInformation(...),  // optional
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
var instance = JsonConvert.DeserializeObject<LegalEntity>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [Relationship](Relationship.md) — used in `Relationships`
- [CounterpartyRiskInformation](CounterpartyRiskInformation.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

