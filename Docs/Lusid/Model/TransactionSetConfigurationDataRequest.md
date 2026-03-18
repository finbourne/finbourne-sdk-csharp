# Finbourne.Sdk.Lusid.Model.TransactionSetConfigurationDataRequest

A bundle of requests to configure a set of transaction types.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionConfigRequests** | [List&lt;TransactionConfigurationDataRequest&gt;](TransactionConfigurationDataRequest.md) | Required | Collection of transaction type models |
| **SideConfigRequests** | [List&lt;SideConfigurationDataRequest&gt;](SideConfigurationDataRequest.md) | Optional | Collection of side definition requests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSetConfigurationDataRequest(
    transactionConfigRequests: new List<TransactionConfigurationDataRequest>(),  // required — Collection of transaction type models
    sideConfigRequests: new List<SideConfigurationDataRequest>()  // optional — Collection of side definition requests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSetConfigurationDataRequest>(json);
```


## Related Models

- [TransactionConfigurationDataRequest](TransactionConfigurationDataRequest.md) — used in `TransactionConfigRequests`
- [SideConfigurationDataRequest](SideConfigurationDataRequest.md) — used in `SideConfigRequests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

