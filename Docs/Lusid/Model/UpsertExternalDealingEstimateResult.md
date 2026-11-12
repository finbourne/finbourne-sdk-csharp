# Finbourne.Sdk.Lusid.Model.UpsertExternalDealingEstimateResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **DealingPoint** | **DateTimeOffset** | Optional | *No description available.* |
| **Late** | **bool** | Optional | *No description available.* |
| **UpsertedEstimates** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | *No description available.* |
| **DeletedEstimates** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertExternalDealingEstimateResult(
    fundId: new ResourceId(...),  // optional
    dealingPoint: DateTimeOffset.Now,  // optional
    late: true,  // optional
    upsertedEstimates: new List<ResourceId>(),  // optional
    deletedEstimates: new List<ResourceId>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertExternalDealingEstimateResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

