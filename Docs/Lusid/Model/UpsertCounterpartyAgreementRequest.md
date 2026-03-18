# Finbourne.Sdk.Lusid.Model.UpsertCounterpartyAgreementRequest

Counterparty Agreement that is to be stored in the convention data store.  There must be only one of these present.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CounterpartyAgreement** | [CounterpartyAgreement](CounterpartyAgreement.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCounterpartyAgreementRequest(
    counterpartyAgreement: new CounterpartyAgreement(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCounterpartyAgreementRequest>(json);
```


## Related Models

- [CounterpartyAgreement](CounterpartyAgreement.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

