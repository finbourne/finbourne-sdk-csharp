# Finbourne.Sdk.Lusid.Model.CashInterest

Interest accrued on posted cash.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **string** | Required | The name of the rate index. |
| **SpreadBps** | **int** | Required | The spread over the index, in basis points. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashInterest(
    index: "...",  // required — The name of the rate index.
    spreadBps: 0  // required — The spread over the index, in basis points.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashInterest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

