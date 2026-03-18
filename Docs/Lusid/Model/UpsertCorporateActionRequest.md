# Finbourne.Sdk.Lusid.Model.UpsertCorporateActionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CorporateActionCode** | **string** | Required | The unique identifier of this corporate action |
| **Description** | **string** | Optional | The description of the corporate action. |
| **AnnouncementDate** | **DateTimeOffset** | Required | The announcement date of the corporate action |
| **ExDate** | **DateTimeOffset** | Required | The ex date of the corporate action |
| **RecordDate** | **DateTimeOffset** | Required | The record date of the corporate action |
| **PaymentDate** | **DateTimeOffset** | Required | The payment date of the corporate action |
| **Transitions** | [List&lt;CorporateActionTransitionRequest&gt;](CorporateActionTransitionRequest.md) | Required | The transitions that result from this corporate action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCorporateActionRequest(
    corporateActionCode: "...",  // required — The unique identifier of this corporate action
    description: "...",  // optional — The description of the corporate action.
    announcementDate: DateTimeOffset.Now,  // required — The announcement date of the corporate action
    exDate: DateTimeOffset.Now,  // required — The ex date of the corporate action
    recordDate: DateTimeOffset.Now,  // required — The record date of the corporate action
    paymentDate: DateTimeOffset.Now,  // required — The payment date of the corporate action
    transitions: new List<CorporateActionTransitionRequest>()  // required — The transitions that result from this corporate action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCorporateActionRequest>(json);
```

- [CorporateActionTransitionRequest](CorporateActionTransitionRequest.md) — used in `Transitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

