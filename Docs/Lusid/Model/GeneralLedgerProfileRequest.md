# Finbourne.Sdk.Lusid.Model.GeneralLedgerProfileRequest

A General Ledger Profile Definition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GeneralLedgerProfileCode** | **string** | Required | The unique code for the General Ledger Profile |
| **DisplayName** | **string** | Required | The name of the General Ledger Profile |
| **Description** | **string** | Optional | A description for the General Ledger Profile |
| **GeneralLedgerProfileMappings** | [List&lt;GeneralLedgerProfileMapping&gt;](GeneralLedgerProfileMapping.md) | Required | Rules for mapping Account or property values to aggregation pattern definitions |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GeneralLedgerProfileRequest(
    generalLedgerProfileCode: "...",  // required — The unique code for the General Ledger Profile
    displayName: "...",  // required — The name of the General Ledger Profile
    description: "...",  // optional — A description for the General Ledger Profile
    generalLedgerProfileMappings: new List<GeneralLedgerProfileMapping>()  // required — Rules for mapping Account or property values to aggregation pattern definitions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneralLedgerProfileRequest>(json);
```

- [GeneralLedgerProfileMapping](GeneralLedgerProfileMapping.md) — used in `GeneralLedgerProfileMappings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

