# Finbourne.Sdk.Horizon.Model.OnboardInstrumentRequest

The full structure of a instrument creation / onboarding request
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataResults** | [List&lt;OpenFigiPermIdResult&gt;](OpenFigiPermIdResult.md) | Required | Enumerable packed OpenFigi/PermId information used to create instruments |
| **PrimaryVendorKey** | **string** | Optional | Primary vendor used to master instrument from Unknown to an asset type |
| **SecondaryVendorKeys** | **List&lt;string&gt;** | Optional | Secondary vendors used to decorate additional properties |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new OnboardInstrumentRequest(
    dataResults: new List<OpenFigiPermIdResult>(),  // required — Enumerable packed OpenFigi/PermId information used to create instruments
    primaryVendorKey: "...",  // optional — Primary vendor used to master instrument from Unknown to an asset type
    secondaryVendorKeys:   // optional — Secondary vendors used to decorate additional properties
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OnboardInstrumentRequest>(json);
```


## Related Models

- [OpenFigiPermIdResult](OpenFigiPermIdResult.md) — used in `DataResults`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

