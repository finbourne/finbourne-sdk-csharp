# Finbourne.Sdk.Lusid.Model.IgnoredDistributionTag

A distribution character tag the run did not pool by, on one account's lines.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GlCode** | **string** | Required | The general ledger account of the tagged lines. |
| **LineCount** | **int** | Required | How many of the account&#39;s lines carried the ignored tag. |
| **Amount** | **decimal** | Required | The journal amount of the tagged lines, debits positive. |
| **Reason** | **string** | Required | Why the tag was ignored. Available values: NotPnlLine (the tagged line is not a profit and loss line, such as the cash leg of a tagged journal), CapabilityForbidden (the fund&#39;s DistributionCharacterSource capability is Forbidden, so characters come from buckets alone). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IgnoredDistributionTag(
    glCode: "...",  // required — The general ledger account of the tagged lines.
    lineCount: 0,  // required — How many of the account&#39;s lines carried the ignored tag.
    amount: 0.0d,  // required — The journal amount of the tagged lines, debits positive.
    reason: "..."  // required — Why the tag was ignored. Available values: NotPnlLine (the tagged line is not a profit and loss line, such as the cash leg of a tagged journal), CapabilityForbidden (the fund&#39;s DistributionCharacterSource capability is Forbidden, so characters come from buckets alone).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IgnoredDistributionTag>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

