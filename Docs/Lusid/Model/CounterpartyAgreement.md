# Finbourne.Sdk.Lusid.Model.CounterpartyAgreement

Represents the legal agreement between two parties engaged in an OTC transaction.  A typical example would be a 2002 ISDA Master Agreement, signed by two legal entities on a given date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | A user-defined display label for the Counterparty Agreement. |
| **AgreementType** | **string** | Required | A user-defined field to capture the type of agreement this represents. Examples might be \&quot;ISDA 2002 Master Agreement\&quot; or \&quot;ISDA 1992 Master Agreement\&quot;. |
| **CounterpartySignatory** | [CounterpartySignatory](CounterpartySignatory.md) | Required | *No description available.* |
| **DatedAsOf** | **DateTimeOffset** | Required | The date on which the CounterpartyAgreement was signed by both parties. |
| **CreditSupportAnnexId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CounterpartyAgreement(
    displayName: "...",  // required — A user-defined display label for the Counterparty Agreement.
    agreementType: "...",  // required — A user-defined field to capture the type of agreement this represents. Examples might be \&quot;ISDA 2002 Master Agreement\&quot; or \&quot;ISDA 1992 Master Agreement\&quot;.
    counterpartySignatory: new CounterpartySignatory(...),  // required
    datedAsOf: DateTimeOffset.Now,  // required — The date on which the CounterpartyAgreement was signed by both parties.
    creditSupportAnnexId: new ResourceId(...),  // required
    id: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CounterpartyAgreement>(json);
```

- [CounterpartySignatory](CounterpartySignatory.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

