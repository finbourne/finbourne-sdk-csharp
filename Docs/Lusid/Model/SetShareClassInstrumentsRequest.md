# Finbourne.Sdk.Lusid.Model.SetShareClassInstrumentsRequest

The request used to create a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassInstrumentScopes** | **List&lt;string&gt;** | Required | The scopes in which the instruments lie, currently limited to one. |
| **ShareClassInstruments** | [List&lt;InstrumentResolutionDetail&gt;](InstrumentResolutionDetail.md) | Required | Details the user-provided instrument identifiers and the instrument resolved from them. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetShareClassInstrumentsRequest(
    shareClassInstrumentScopes: ,  // required — The scopes in which the instruments lie, currently limited to one.
    shareClassInstruments: new List<InstrumentResolutionDetail>()  // required — Details the user-provided instrument identifiers and the instrument resolved from them.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetShareClassInstrumentsRequest>(json);
```

- [InstrumentResolutionDetail](InstrumentResolutionDetail.md) — used in `ShareClassInstruments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

