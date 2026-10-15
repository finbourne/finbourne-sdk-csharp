# Finbourne.Sdk.Lusid.Model.MarginCalculation

How the margin requirement for an item is calculated. The method field selects the method and the  remaining fields are the ones that method uses.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Method** | **string** | Required | The calculation method. One of NetMtm, Ccp, GmraExposure, GmslaRcv, HouseRules, Simm, RegulatoryGrid or CcpIngested. Available values: NetMtm, Ccp, GmraExposure, GmslaRcv, HouseRules, Simm, RegulatoryGrid, CcpIngested. |
| **ExposureMethod** | **string** | Optional | For GmraExposure, the exposure method. One of Gmra2011A or Gmra2011B. Available values: Gmra2011A, Gmra2011B. |
| **RepricingPermitted** | **bool?** | Optional | For GmraExposure, whether repricing is permitted. |
| **MarginPercentage** | **decimal?** | Optional | For GmslaRcv, the margin percentage applied to the loan value. |
| **LendingFeeBps** | **int?** | Optional | For GmslaRcv, the lending fee in basis points. |
| **CreditLine** | **decimal?** | Optional | For HouseRules, the credit line extended to the counterparty. |
| **ThresholdAllocation** | [ThresholdAllocation](ThresholdAllocation.md) | Optional | *No description available.* |
| **Ccp** | **string** | Optional | For CcpIngested, the name of the central counterparty. |
| **FcmAddOn** | **decimal?** | Optional | For CcpIngested, the add-on charged by the futures commission merchant. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginCalculation(
    method: "...",  // required — The calculation method. One of NetMtm, Ccp, GmraExposure, GmslaRcv, HouseRules, Simm, RegulatoryGrid or CcpIngested. Available values: NetMtm, Ccp, GmraExposure, GmslaRcv, HouseRules, Simm, RegulatoryGrid, CcpIngested.
    exposureMethod: "...",  // optional — For GmraExposure, the exposure method. One of Gmra2011A or Gmra2011B. Available values: Gmra2011A, Gmra2011B.
    repricingPermitted: true,  // optional — For GmraExposure, whether repricing is permitted.
    marginPercentage: 0.0d,  // optional — For GmslaRcv, the margin percentage applied to the loan value.
    lendingFeeBps: 0,  // optional — For GmslaRcv, the lending fee in basis points.
    creditLine: 0.0d,  // optional — For HouseRules, the credit line extended to the counterparty.
    thresholdAllocation: new ThresholdAllocation(...),  // optional
    ccp: "...",  // optional — For CcpIngested, the name of the central counterparty.
    fcmAddOn: 0.0d  // optional — For CcpIngested, the add-on charged by the futures commission merchant.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginCalculation>(json);
```

- [ThresholdAllocation](ThresholdAllocation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

