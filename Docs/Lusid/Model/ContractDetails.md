# Finbourne.Sdk.Lusid.Model.ContractDetails

Set of identifiers of an existing FlexibleLoan contract.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers. |
| **LusidInstrumentId** | **string** | Optional | LUSID&#39;s internal unique instrument identifier - readonly field, resolved from the instrument identifiers. *(read-only)* |
| **InstrumentScope** | **string** | Optional | The scope in which the FlexibleLoan instrument lies - readonly field, resolved from the instrument identifiers. *(read-only)* |
| **InstrumentName** | **string** | Optional | The name of the FlexibleLoan instrument - readonly field, resolved from the instrument identifiers. *(read-only)* |
| **DomCcy** | **string** | Optional | The domestic currency of the instrument - readonly field, resolved from the instrument identifiers. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ContractDetails(
    identifiers: ,  // required — Unique instrument identifiers.
    lusidInstrumentId: "...",  // optional — LUSID&#39;s internal unique instrument identifier - readonly field, resolved from the instrument identifiers.
    instrumentScope: "...",  // optional — The scope in which the FlexibleLoan instrument lies - readonly field, resolved from the instrument identifiers.
    instrumentName: "...",  // optional — The name of the FlexibleLoan instrument - readonly field, resolved from the instrument identifiers.
    domCcy: "..."  // optional — The domestic currency of the instrument - readonly field, resolved from the instrument identifiers.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ContractDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

