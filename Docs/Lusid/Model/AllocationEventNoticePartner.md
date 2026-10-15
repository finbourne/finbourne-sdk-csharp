# Finbourne.Sdk.Lusid.Model.AllocationEventNoticePartner

The partner a notice is addressed to.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record identifier of the partner. |
| **DisplayName** | **string** | Optional | The display name of the partner. |
| **Commitment** | **decimal** | Required | The partner&#39;s total commitment. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticePartner(
    investorRecordId: "...",  // required — The investor record identifier of the partner.
    displayName: "...",  // optional — The display name of the partner.
    commitment: 0.0d  // required — The partner&#39;s total commitment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticePartner>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

