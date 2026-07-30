# Finbourne.Sdk.Lusid.Model.RecRequiredApproval

An approval slot required for a result set, passed through from the rec definition's review configuration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApprovalCode** | **string** | Required | Client-defined identifier for the approval slot (e.g. &#39;Desk&#39;, &#39;Risk&#39;). |
| **Description** | **string** | Optional | Human-readable label for the approval slot. |
| **CurrentUserCanDecide** | **bool** | Optional | Whether the calling user may decide this approval slot, pre-evaluated at request time. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecRequiredApproval(
    approvalCode: "...",  // required — Client-defined identifier for the approval slot (e.g. &#39;Desk&#39;, &#39;Risk&#39;).
    description: "...",  // optional — Human-readable label for the approval slot.
    currentUserCanDecide: true  // optional — Whether the calling user may decide this approval slot, pre-evaluated at request time.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecRequiredApproval>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

