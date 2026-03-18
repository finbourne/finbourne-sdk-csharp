# Finbourne.Sdk.Lusid.Model.UpsertInvestorRecordRequest

Request to create or update an investor record
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope in which the Investor Record lies. |
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | Unique client-defined identifiers of the Investor Record. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties associated to the Investor Record. |
| **DisplayName** | **string** | Required | The display name of the Investor Record |
| **Description** | **string** | Optional | The description of the Investor Record |
| **Investor** | [InvestorIdentifier](InvestorIdentifier.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInvestorRecordRequest(
    scope: "...",  // required — The scope in which the Investor Record lies.
    identifiers: new Property(...),  // required — Unique client-defined identifiers of the Investor Record.
    properties: new Property(...),  // optional — A set of properties associated to the Investor Record.
    displayName: "...",  // required — The display name of the Investor Record
    description: "...",  // optional — The description of the Investor Record
    investor: new InvestorIdentifier(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInvestorRecordRequest>(json);
```

- [Property](Property.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [InvestorIdentifier](InvestorIdentifier.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

