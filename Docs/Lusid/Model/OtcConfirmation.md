# Finbourne.Sdk.Lusid.Model.OtcConfirmation

For the storage of any information pertinent to the confirmation of an OTC trade. e.g the Counterparty Agreement Code
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CounterpartyAgreementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OtcConfirmation(
    counterpartyAgreementId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OtcConfirmation>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

