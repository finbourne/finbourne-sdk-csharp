# Finbourne.Sdk.Lusid.Model.Bucket

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaxLotId** | **string** | Optional | The identifier of the tax lot this bucket is for. |
| **MovementName** | **string** | Optional | The name of the movement. |
| **HoldingType** | **string** | Optional | The type of the holding. |
| **EconomicBucket** | **string** | Optional | The economic bucket. |
| **EconomicBucketComponent** | **string** | Optional | The economic bucket component. |
| **EconomicBucketVariant** | **string** | Optional | The economic bucket component. |
| **HoldingSign** | **string** | Optional | The holding sign. |
| **Local** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Base** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Units** | **decimal** | Optional | The units. |
| **ActivityDate** | **DateTimeOffset** | Optional | The activity date of the bucket. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Bucket(
    taxLotId: "...",  // optional — The identifier of the tax lot this bucket is for.
    movementName: "...",  // optional — The name of the movement.
    holdingType: "...",  // optional — The type of the holding.
    economicBucket: "...",  // optional — The economic bucket.
    economicBucketComponent: "...",  // optional — The economic bucket component.
    economicBucketVariant: "...",  // optional — The economic bucket component.
    holdingSign: "...",  // optional — The holding sign.
    local: new CurrencyAndAmount(...),  // optional
    varBase: new CurrencyAndAmount(...),  // optional
    units: 0.0d,  // optional — The units.
    activityDate: DateTimeOffset.Now  // optional — The activity date of the bucket.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Bucket>(json);
```

- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

