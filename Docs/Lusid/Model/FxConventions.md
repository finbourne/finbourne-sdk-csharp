# Finbourne.Sdk.Lusid.Model.FxConventions

The conventions for the calculation of FX fixings, where the fixing rate is expected to be the amount of  DomCcy per unit of FgnCcy.  As an example, assume the required fixing is the WM/R 4pm mid closing rate for the USD amount per 1 EUR.  This is published with RIC EURUSDFIXM=WM, which would be the FixingReference, with FgnCcy EUR and DomCcy USD.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FgnCcy** | **string** | Required | The foreign currency |
| **DomCcy** | **string** | Required | The domestic currency |
| **FixingReference** | **string** | Required | The reference name used to find the desired quote |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxConventions(
    fgnCcy: "...",  // required — The foreign currency
    domCcy: "...",  // required — The domestic currency
    fixingReference: "..."  // required — The reference name used to find the desired quote
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

