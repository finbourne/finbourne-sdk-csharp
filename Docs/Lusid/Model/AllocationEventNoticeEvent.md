# Finbourne.Sdk.Lusid.Model.AllocationEventNoticeEvent

The allocation event a notice is issued for.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | The type of the allocation event. |
| **EventDate** | **DateTimeOffset** | Required | The effective date of the allocation event. |
| **NoticeDate** | **DateTimeOffset?** | Optional | The date the notice is issued. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the payment is due. |
| **Status** | **string** | Required | The status of the allocation event. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticeEvent(
    id: new ResourceId(...),  // required
    type: "...",  // required — The type of the allocation event.
    eventDate: DateTimeOffset.Now,  // required — The effective date of the allocation event.
    noticeDate: DateTimeOffset.Now,  // optional — The date the notice is issued.
    dueDate: DateTimeOffset.Now,  // optional — The date the payment is due.
    status: "..."  // required — The status of the allocation event.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticeEvent>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

