# Finbourne.Sdk.Lusid.Model.UpsertLegalEntityRequest

Request to create or update an legal entity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | The identifiers the legal entity will be upserted with.The provided keys should be idTypeScope, idTypeCode, code |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Legal Entity. |
| **DisplayName** | **string** | Required | The display name of the Legal Entity |
| **Description** | **string** | Optional | The description of the Legal Entity |
| **CounterpartyRiskInformation** | [CounterpartyRiskInformation](CounterpartyRiskInformation.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertLegalEntityRequest(
    identifiers: new Property(...),  // required — The identifiers the legal entity will be upserted with.The provided keys should be idTypeScope, idTypeCode, code
    properties: new Property(...),  // optional — A set of properties associated to the Legal Entity.
    displayName: "...",  // required — The display name of the Legal Entity
    description: "...",  // optional — The description of the Legal Entity
    counterpartyRiskInformation: new CounterpartyRiskInformation(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertLegalEntityRequest>(json);
```


## Related Models

- [Property](Property.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [CounterpartyRiskInformation](CounterpartyRiskInformation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

