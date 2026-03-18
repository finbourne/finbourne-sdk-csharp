# Finbourne.Sdk.Lusid.Model.CreateRelationDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope that the relation exists in. |
| **Code** | **string** | Required | The code of the relation. Together with the scope this uniquely defines the relation. |
| **SourceEntityDomain** | **string** | Required | The entity domain of the source entity object must be, allowed values are \&quot;Portfolio\&quot; and \&quot;Person\&quot; |
| **TargetEntityDomain** | **string** | Required | The entity domain of the target entity object must be, allowed values are \&quot;Portfolio\&quot; and \&quot;Person\&quot; |
| **DisplayName** | **string** | Required | The display name of the relation. |
| **OutwardDescription** | **string** | Required | The description to relate source entity object and target entity object. |
| **InwardDescription** | **string** | Required | The description to relate target entity object and source entity object. |
| **LifeTime** | **string** | Optional | Describes how the relations can change over time, allowed values are \&quot;Perpetual\&quot; and \&quot;TimeVariant\&quot; |
| **ConstraintStyle** | **string** | Optional | Describes the uniqueness and cardinality for relations with a specific source entity object and relations under this definition. Allowed values are \&quot;Property\&quot; and \&quot;Collection\&quot;, defaults to \&quot;Collection\&quot; if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateRelationDefinitionRequest(
    scope: "...",  // required — The scope that the relation exists in.
    code: "...",  // required — The code of the relation. Together with the scope this uniquely defines the relation.
    sourceEntityDomain: "...",  // required — The entity domain of the source entity object must be, allowed values are \&quot;Portfolio\&quot; and \&quot;Person\&quot;
    targetEntityDomain: "...",  // required — The entity domain of the target entity object must be, allowed values are \&quot;Portfolio\&quot; and \&quot;Person\&quot;
    displayName: "...",  // required — The display name of the relation.
    outwardDescription: "...",  // required — The description to relate source entity object and target entity object.
    inwardDescription: "...",  // required — The description to relate target entity object and source entity object.
    lifeTime: "...",  // optional — Describes how the relations can change over time, allowed values are \&quot;Perpetual\&quot; and \&quot;TimeVariant\&quot;
    constraintStyle: "..."  // optional — Describes the uniqueness and cardinality for relations with a specific source entity object and relations under this definition. Allowed values are \&quot;Property\&quot; and \&quot;Collection\&quot;, defaults to \&quot;Collection\&quot; if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRelationDefinitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

