# Finbourne.Sdk.Lusid.Model.CorporateAction

A corporate action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CorporateActionCode** | **string** | Required | The unique identifier of this corporate action |
| **Description** | **string** | Optional | The description of the corporate action. |
| **AnnouncementDate** | **DateTimeOffset** | Optional | The announcement date of the corporate action |
| **ExDate** | **DateTimeOffset** | Optional | The ex date of the corporate action |
| **RecordDate** | **DateTimeOffset** | Optional | The record date of the corporate action |
| **PaymentDate** | **DateTimeOffset** | Optional | The payment date of the corporate action |
| **Transitions** | [List&lt;CorporateActionTransition&gt;](CorporateActionTransition.md) | Optional | The transitions that result from this corporate action |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateAction(
    corporateActionCode: "...",  // required — The unique identifier of this corporate action
    description: "...",  // optional — The description of the corporate action.
    announcementDate: DateTimeOffset.Now,  // optional — The announcement date of the corporate action
    exDate: DateTimeOffset.Now,  // optional — The ex date of the corporate action
    recordDate: DateTimeOffset.Now,  // optional — The record date of the corporate action
    paymentDate: DateTimeOffset.Now,  // optional — The payment date of the corporate action
    transitions: new List<CorporateActionTransition>()  // optional — The transitions that result from this corporate action
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorporateAction>(json);
```

- [CorporateActionTransition](CorporateActionTransition.md) — used in `Transitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

