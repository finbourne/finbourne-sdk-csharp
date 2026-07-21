# Finbourne.Sdk.Lusid.Model.ApportionmentMemberFactor

One member share class's outcome within an apportionment result: the base value the method produced for it  and the resulting apportionment factor.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MemberIdentifier** | **string** | Required | The member share class&#39;s short code. |
| **FundScope** | **string** | Optional | The scope of the fund the member share class belongs to. |
| **FundCode** | **string** | Optional | The code of the fund the member share class belongs to. |
| **BaseValue** | **decimal?** | Optional | The base value the method produced for the member, or null for the SetFactor method. |
| **ApportionmentFactor** | **decimal** | Required | The member&#39;s apportionment factor: its base value over the total across the group or fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApportionmentMemberFactor(
    memberIdentifier: "...",  // required — The member share class&#39;s short code.
    fundScope: "...",  // optional — The scope of the fund the member share class belongs to.
    fundCode: "...",  // optional — The code of the fund the member share class belongs to.
    baseValue: 0.0d,  // optional — The base value the method produced for the member, or null for the SetFactor method.
    apportionmentFactor: 0.0d  // required — The member&#39;s apportionment factor: its base value over the total across the group or fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApportionmentMemberFactor>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

