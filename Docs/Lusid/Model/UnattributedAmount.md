# Finbourne.Sdk.Lusid.Model.UnattributedAmount

An amount on the income summary an allocation run could not attribute to any pool.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GlCode** | **string** | Required | The general ledger account the unattributed amount sits in. |
| **Amount** | **decimal** | Required | The amount allocated to the partner. |
| **Reason** | **string** | Required | Why the amount could not be attributed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnattributedAmount(
    glCode: "...",  // required — The general ledger account the unattributed amount sits in.
    amount: 0.0d,  // required — The amount allocated to the partner.
    reason: "..."  // required — Why the amount could not be attributed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnattributedAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

