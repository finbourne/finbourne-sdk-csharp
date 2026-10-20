# Finbourne.Sdk.Lusid.Model.MarginCallKey

The parts that identify a margin call: its run and the call's business key.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run the call belongs to. |
| **AgreementScope** | **string** | Required | The scope of the call&#39;s collateral agreement. |
| **AgreementCode** | **string** | Required | The code of the call&#39;s collateral agreement. |
| **Item** | **string** | Required | The margin item of the call. |
| **MarginType** | **string** | Required | The margin type of the call. Currently VariationMargin. |
| **Direction** | **string** | Required | Who posts under the call: WePost, TheyPost or None. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginCallKey(
    runId: "...",  // required — The run the call belongs to.
    agreementScope: "...",  // required — The scope of the call&#39;s collateral agreement.
    agreementCode: "...",  // required — The code of the call&#39;s collateral agreement.
    item: "...",  // required — The margin item of the call.
    marginType: "...",  // required — The margin type of the call. Currently VariationMargin.
    direction: "..."  // required — Who posts under the call: WePost, TheyPost or None.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginCallKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

