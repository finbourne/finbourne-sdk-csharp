# Finbourne.Sdk.Lusid.Model.Person

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the Person |
| **Description** | **string** | Optional | The description of the Person |
| **Href** | **string** | Optional | The specifc Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **LusidPersonId** | **string** | Optional | The unique LUSID Person Identifier of the Person. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Unique client-defined identifiers of the Person. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Person. There can be multiple properties associated with a property key. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the Person. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Person(
    displayName: "...",  // optional — The display name of the Person
    description: "...",  // optional — The description of the Person
    href: "...",  // optional — The specifc Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    lusidPersonId: "...",  // optional — The unique LUSID Person Identifier of the Person.
    identifiers: new Property(...),  // optional — Unique client-defined identifiers of the Person.
    properties: new Property(...),  // optional — A set of properties associated to the Person. There can be multiple properties associated with a property key.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the Person.
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
var instance = JsonConvert.DeserializeObject<Person>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [Relationship](Relationship.md) — used in `Relationships`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

