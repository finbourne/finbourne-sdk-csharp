# Finbourne.Sdk.Lusid.Model.FundStructureCloseRequest

The request to close a fund structure: finalise the named valuation point on every member, members first.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ValuationPointCode** | **string** | Required | The code of the valuation point to finalise on every member fund. |
| **NavTypeCode** | **string** | Optional | The NAV type to finalise under. Defaults to each fund&#39;s primary NAV type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureCloseRequest(
    valuationPointCode: "...",  // required — The code of the valuation point to finalise on every member fund.
    navTypeCode: "..."  // optional — The NAV type to finalise under. Defaults to each fund&#39;s primary NAV type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureCloseRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

