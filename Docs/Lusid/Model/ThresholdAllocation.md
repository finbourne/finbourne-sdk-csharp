# Finbourne.Sdk.Lusid.Model.ThresholdAllocation

How a threshold is split between the two parties.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **We** | **decimal** | Required | Our share of the threshold. |
| **They** | **decimal** | Required | The counterparty&#39;s share of the threshold. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ThresholdAllocation(
    we: 0.0d,  // required — Our share of the threshold.
    they: 0.0d  // required — The counterparty&#39;s share of the threshold.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ThresholdAllocation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

