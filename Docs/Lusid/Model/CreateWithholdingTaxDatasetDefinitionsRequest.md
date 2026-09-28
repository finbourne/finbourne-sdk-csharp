# Finbourne.Sdk.Lusid.Model.CreateWithholdingTaxDatasetDefinitionsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnomalyDataset** | [CreateWithholdingTaxDataset](CreateWithholdingTaxDataset.md) | Required | *No description available.* |
| **MainDataset** | [CreateWithholdingTaxDataset](CreateWithholdingTaxDataset.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateWithholdingTaxDatasetDefinitionsRequest(
    anomalyDataset: new CreateWithholdingTaxDataset(...),  // required
    mainDataset: new CreateWithholdingTaxDataset(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateWithholdingTaxDatasetDefinitionsRequest>(json);
```


## Related Models

- [CreateWithholdingTaxDataset](CreateWithholdingTaxDataset.md)
- [CreateWithholdingTaxDataset](CreateWithholdingTaxDataset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

