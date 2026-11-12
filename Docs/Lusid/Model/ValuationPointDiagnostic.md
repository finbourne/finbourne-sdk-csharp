# Finbourne.Sdk.Lusid.Model.ValuationPointDiagnostic

Something found while striking a valuation point that did not stop it but should be looked at.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | What kind of finding this is. &#39;OwnershipDrift&#39;: a fund structure holder&#39;s declared sharing percentage in a held member differs from the share its contributions make of that member&#39;s capital by enough to misallocate more of the period&#39;s P&amp;L than the holder&#39;s drift materiality warning amount allows. &#39;FeeStrikeFailed&#39;: the fees struck when the valuation point was last created or updated failed, so its lines carry no fee transactions and it cannot be accepted until they are struck again. |
| **Message** | **string** | Required | What was found and what to do about it. |
| **Details** | **Dictionary&lt;string, string&gt;** | Optional | The values the finding was made on, by name. For &#39;OwnershipDrift&#39;: holder, member, declaredShare, actualShare, delta (actual less declared) and impact (the P&amp;L the drift would misallocate this period). For &#39;FeeStrikeFailed&#39;: failureType and failureMessage, the cause of the failed strike. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointDiagnostic(
    type: "...",  // required — What kind of finding this is. &#39;OwnershipDrift&#39;: a fund structure holder&#39;s declared sharing percentage in a held member differs from the share its contributions make of that member&#39;s capital by enough to misallocate more of the period&#39;s P&amp;L than the holder&#39;s drift materiality warning amount allows. &#39;FeeStrikeFailed&#39;: the fees struck when the valuation point was last created or updated failed, so its lines carry no fee transactions and it cannot be accepted until they are struck again.
    message: "...",  // required — What was found and what to do about it.
    details:   // optional — The values the finding was made on, by name. For &#39;OwnershipDrift&#39;: holder, member, declaredShare, actualShare, delta (actual less declared) and impact (the P&amp;L the drift would misallocate this period). For &#39;FeeStrikeFailed&#39;: failureType and failureMessage, the cause of the failed strike.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointDiagnostic>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

