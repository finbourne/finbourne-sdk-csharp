# Finbourne.Sdk.Lusid.Model.ShareClassDealingBreakdown

The breakdown of Dealing for a Share Class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClassDealing** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Required | Bucket of detail for any &#39;Dealing&#39; specific to the share class that has occured inside the queried period. |
| **ClassDealingUnits** | [Dictionary&lt;string, Amount&gt;](Amount.md) | Required | Bucket of detail for any &#39;Dealing&#39; units specific to the share class that has occured inside the queried period. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassDealingBreakdown(
    classDealing: new ShareClassAmount(...),  // required — Bucket of detail for any &#39;Dealing&#39; specific to the share class that has occured inside the queried period.
    classDealingUnits: new Amount(...)  // required — Bucket of detail for any &#39;Dealing&#39; units specific to the share class that has occured inside the queried period.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassDealingBreakdown>(json);
```


## Related Models

- [ShareClassAmount](ShareClassAmount.md) — used in `ClassDealing`
- [Amount](Amount.md) — used in `ClassDealingUnits`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

