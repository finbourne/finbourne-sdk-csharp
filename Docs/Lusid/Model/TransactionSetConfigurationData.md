# Finbourne.Sdk.Lusid.Model.TransactionSetConfigurationData

A collection of the data required to configure transaction types..
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionConfigs** | [List&lt;TransactionConfigurationData&gt;](TransactionConfigurationData.md) | Required | Collection of transaction type models |
| **SideDefinitions** | [List&lt;SideConfigurationData&gt;](SideConfigurationData.md) | Optional | Collection of side definitions |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSetConfigurationData(
    transactionConfigs: new List<TransactionConfigurationData>(),  // required — Collection of transaction type models
    sideDefinitions: new List<SideConfigurationData>(),  // optional — Collection of side definitions
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSetConfigurationData>(json);
```


## Related Models

- [TransactionConfigurationData](TransactionConfigurationData.md) — used in `TransactionConfigs`
- [SideConfigurationData](SideConfigurationData.md) — used in `SideDefinitions`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

