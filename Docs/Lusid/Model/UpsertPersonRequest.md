# Finbourne.Sdk.Lusid.Model.UpsertPersonRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | The identifiers the person will be upserted with.The provided keys should be idTypeScope, idTypeCode, code |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Person. There can be multiple properties associated with a property key. |
| **DisplayName** | **string** | Required | The display name of the Person |
| **Description** | **string** | Optional | The description of the Person |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertPersonRequest(
    identifiers: new Property(...),  // required — The identifiers the person will be upserted with.The provided keys should be idTypeScope, idTypeCode, code
    properties: new Property(...),  // optional — A set of properties associated to the Person. There can be multiple properties associated with a property key.
    displayName: "...",  // required — The display name of the Person
    description: "..."  // optional — The description of the Person
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertPersonRequest>(json);
```


## Related Models

- [Property](Property.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

