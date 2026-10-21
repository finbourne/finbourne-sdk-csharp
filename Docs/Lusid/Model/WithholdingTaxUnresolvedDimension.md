# Finbourne.Sdk.Lusid.Model.WithholdingTaxUnresolvedDimension

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReadFrom** | **List&lt;string&gt;** | Required | What booking reads the dimension from: Transaction, Portfolio or Fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxUnresolvedDimension(
    readFrom:   // required — What booking reads the dimension from: Transaction, Portfolio or Fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxUnresolvedDimension>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

