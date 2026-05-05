# Finbourne.Sdk.Lusid.Model.TransactionFeeCapitalisation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Capitalisation** | **string** | Optional | Whether the transaction fee should be capitalised, not capitalised, or conditionally capitalised. Available values: Capitalised, NonCapitalised, Conditional. |
| **CapitalisedCondition** | **string** | Optional | The condition that determines whether the fee is capitalised when applied to the transaction. Required only when Capitalisation is &#39;Conditional&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionFeeCapitalisation(
    capitalisation: "...",  // optional — Whether the transaction fee should be capitalised, not capitalised, or conditionally capitalised. Available values: Capitalised, NonCapitalised, Conditional.
    capitalisedCondition: "..."  // optional — The condition that determines whether the fee is capitalised when applied to the transaction. Required only when Capitalisation is &#39;Conditional&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionFeeCapitalisation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

