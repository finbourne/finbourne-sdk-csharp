# Finbourne.Sdk.Lusid.Model.ApportionmentInput

One named amount that contributed to a member share class's apportionment base value - the workings behind  the figure rather than the figure alone. A member's inputs always sum to its base value.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The input&#39;s identifier within its apportionment method, for example &#39;openingNav&#39;. |
| **DisplayName** | **string** | Required | The input&#39;s human-readable name, for example &#39;Opening NAV&#39;. |
| **Value** | **decimal** | Required | The input&#39;s contribution to the base value, signed as it contributes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApportionmentInput(
    code: "...",  // required — The input&#39;s identifier within its apportionment method, for example &#39;openingNav&#39;.
    displayName: "...",  // required — The input&#39;s human-readable name, for example &#39;Opening NAV&#39;.
    value: 0.0d  // required — The input&#39;s contribution to the base value, signed as it contributes.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApportionmentInput>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

