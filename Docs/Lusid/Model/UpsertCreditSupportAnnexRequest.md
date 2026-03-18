# Finbourne.Sdk.Lusid.Model.UpsertCreditSupportAnnexRequest

Credit Support Annex information. The interaction in terms of margining requirements between a set of trades for a given counterparty.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CreditSupportAnnex** | [CreditSupportAnnex](CreditSupportAnnex.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCreditSupportAnnexRequest(
    creditSupportAnnex: new CreditSupportAnnex(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCreditSupportAnnexRequest>(json);
```


## Related Models

- [CreditSupportAnnex](CreditSupportAnnex.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

