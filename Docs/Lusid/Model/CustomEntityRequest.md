# Finbourne.Sdk.Lusid.Model.CustomEntityRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | A display label for the custom entity. |
| **Description** | **string** | Required | A description of the custom entity. |
| **Identifiers** | [List&lt;CustomEntityId&gt;](CustomEntityId.md) | Required | The identifiers the custom entity will be upserted with. |
| **Fields** | [List&lt;CustomEntityField&gt;](CustomEntityField.md) | Optional | The fields that decorate the custom entity. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties that decorate the custom entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityRequest(
    displayName: "...",  // required — A display label for the custom entity.
    description: "...",  // required — A description of the custom entity.
    identifiers: new List<CustomEntityId>(),  // required — The identifiers the custom entity will be upserted with.
    fields: new List<CustomEntityField>(),  // optional — The fields that decorate the custom entity.
    properties: new Property(...)  // optional — The properties that decorate the custom entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityRequest>(json);
```

- [CustomEntityId](CustomEntityId.md) — used in `Identifiers`
- [CustomEntityField](CustomEntityField.md) — used in `Fields`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

