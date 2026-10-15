# Finbourne.Sdk.Lusid.Model.WhtParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WhtConfig** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaxCountry** | **string** | Required | The holder&#39;s country of tax residence, matched against the taxCountry field of the rate datasets. |
| **ProfileType** | **string** | Required | The holder&#39;s tax profile, matched against the profileType field of the rate datasets. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WhtParameters(
    whtConfig: new ResourceId(...),  // required
    taxCountry: "...",  // required — The holder&#39;s country of tax residence, matched against the taxCountry field of the rate datasets.
    profileType: "..."  // required — The holder&#39;s tax profile, matched against the profileType field of the rate datasets.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WhtParameters>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

