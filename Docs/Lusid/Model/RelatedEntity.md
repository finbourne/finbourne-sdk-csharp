# Finbourne.Sdk.Lusid.Model.RelatedEntity

Information about the other related entity in the relationship
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of the entity. |
| **EntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the other related entity in the relationship. It contains &#39;scope&#39; and &#39;code&#39; as keys for identifiers of a Portfolio or Portfolio Group, or &#39;idTypeScope&#39;, &#39;idTypeCode&#39;, &#39;code&#39; as keys for identifiers of a Person or Legal entity, or &#39;scope&#39;, &#39;identifierType&#39;, &#39;identifierValue&#39; as keys for identifiers of an Instrument |
| **DisplayName** | **string** | Required | The display name of the entity. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties of the entity. This field is empty until further notice. |
| **Scope** | **string** | Optional | The scope of the identifier |
| **LusidUniqueId** | [LusidUniqueId](LusidUniqueId.md) | Optional | *No description available.* |
| **Identifiers** | [List&lt;EntityIdentifier&gt;](EntityIdentifier.md) | Required | The identifiers of the related entity in the relationship. |
| **Href** | **string** | Optional | The link to the entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelatedEntity(
    entityType: "...",  // required — The type of the entity.
    entityId: ,  // required — The identifier of the other related entity in the relationship. It contains &#39;scope&#39; and &#39;code&#39; as keys for identifiers of a Portfolio or Portfolio Group, or &#39;idTypeScope&#39;, &#39;idTypeCode&#39;, &#39;code&#39; as keys for identifiers of a Person or Legal entity, or &#39;scope&#39;, &#39;identifierType&#39;, &#39;identifierValue&#39; as keys for identifiers of an Instrument
    displayName: "...",  // required — The display name of the entity.
    properties: new Property(...),  // optional — The properties of the entity. This field is empty until further notice.
    scope: "...",  // optional — The scope of the identifier
    lusidUniqueId: new LusidUniqueId(...),  // optional
    identifiers: new List<EntityIdentifier>(),  // required — The identifiers of the related entity in the relationship.
    href: "..."  // optional — The link to the entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelatedEntity>(json);
```

- [Property](Property.md) — used in `Properties`
- [LusidUniqueId](LusidUniqueId.md)
- [EntityIdentifier](EntityIdentifier.md) — used in `Identifiers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

