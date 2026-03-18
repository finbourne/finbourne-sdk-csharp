# Finbourne.Sdk.Lusid.Model.CounterpartySignatory

The counterpartyAgreement is signed by two parties, one of which is implicitly the LUSID user.  The CounterpartySignatory represents the 'other side' of the agreement.  It comprises a name and identifier for a Legal Entity in LUSID.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | A user-defined name or label for the counterparty signatory.  There is no requirement for this to match the \&quot;displayName\&quot; of the legal entity. |
| **LegalEntityIdentifier** | [TypedResourceId](TypedResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CounterpartySignatory(
    name: "...",  // required — A user-defined name or label for the counterparty signatory.  There is no requirement for this to match the \&quot;displayName\&quot; of the legal entity.
    legalEntityIdentifier: new TypedResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CounterpartySignatory>(json);
```

- [TypedResourceId](TypedResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

