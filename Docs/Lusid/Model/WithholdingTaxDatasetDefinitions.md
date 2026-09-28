# Finbourne.Sdk.Lusid.Model.WithholdingTaxDatasetDefinitions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnomalyDataset** | [WithholdingTaxDataset](WithholdingTaxDataset.md) | Required | *No description available.* |
| **MainDataset** | [WithholdingTaxDataset](WithholdingTaxDataset.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxDatasetDefinitions(
    anomalyDataset: new WithholdingTaxDataset(...),  // required
    mainDataset: new WithholdingTaxDataset(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxDatasetDefinitions>(json);
```


## Related Models

- [WithholdingTaxDataset](WithholdingTaxDataset.md)
- [WithholdingTaxDataset](WithholdingTaxDataset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

