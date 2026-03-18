# Finbourne.Sdk.Lusid.Model.CreateRelationshipDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope that the relationship definition exists in. |
| **Code** | **string** | Required | The code of the relationship definition. Together with the scope this uniquely defines the relationship definition. |
| **SourceEntityType** | **string** | Required | The entity type of the source entity object. Allowed values are &#39;Portfolio&#39;, &#39;PortfolioGroup&#39;, &#39;Person&#39;, &#39;LegalEntity&#39;, &#39;Instrument&#39; or a custom entity type prefixed with &#39;~&#39;. |
| **TargetEntityType** | **string** | Required | The entity type of the target entity object. Allowed values are &#39;Portfolio&#39;, &#39;PortfolioGroup&#39;, &#39;Person&#39;, &#39;LegalEntity&#39;, &#39;Instrument&#39; or a custom entity type prefixed with &#39;~&#39;. |
| **DisplayName** | **string** | Required | The display name of the relationship definition. |
| **OutwardDescription** | **string** | Required | The description to relate source entity object and target entity object. |
| **InwardDescription** | **string** | Required | The description to relate target entity object and source entity object. |
| **LifeTime** | **string** | Optional | Describes how the relationships can change over time. Allowed values are &#39;Perpetual&#39; and &#39;TimeVariant&#39;, defaults to &#39;Perpetual&#39; if not specified. |
| **RelationshipCardinality** | **string** | Optional | Describes the cardinality of the relationship with a specific source entity object and relationships under this definition. Allowed values are &#39;ManyToMany&#39; and &#39;ManyToOne&#39;, defaults to &#39;ManyToMany&#39; if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateRelationshipDefinitionRequest(
    scope: "...",  // required — The scope that the relationship definition exists in.
    code: "...",  // required — The code of the relationship definition. Together with the scope this uniquely defines the relationship definition.
    sourceEntityType: "...",  // required — The entity type of the source entity object. Allowed values are &#39;Portfolio&#39;, &#39;PortfolioGroup&#39;, &#39;Person&#39;, &#39;LegalEntity&#39;, &#39;Instrument&#39; or a custom entity type prefixed with &#39;~&#39;.
    targetEntityType: "...",  // required — The entity type of the target entity object. Allowed values are &#39;Portfolio&#39;, &#39;PortfolioGroup&#39;, &#39;Person&#39;, &#39;LegalEntity&#39;, &#39;Instrument&#39; or a custom entity type prefixed with &#39;~&#39;.
    displayName: "...",  // required — The display name of the relationship definition.
    outwardDescription: "...",  // required — The description to relate source entity object and target entity object.
    inwardDescription: "...",  // required — The description to relate target entity object and source entity object.
    lifeTime: "...",  // optional — Describes how the relationships can change over time. Allowed values are &#39;Perpetual&#39; and &#39;TimeVariant&#39;, defaults to &#39;Perpetual&#39; if not specified.
    relationshipCardinality: "..."  // optional — Describes the cardinality of the relationship with a specific source entity object and relationships under this definition. Allowed values are &#39;ManyToMany&#39; and &#39;ManyToOne&#39;, defaults to &#39;ManyToMany&#39; if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRelationshipDefinitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

