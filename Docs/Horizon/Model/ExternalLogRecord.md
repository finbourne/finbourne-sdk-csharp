# Finbourne.Sdk.Horizon.Model.ExternalLogRecord

Represents an external log record.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Logid** | **long** | Required | The unique log identifier. |
| **Parentlogid** | **long?** | Optional | The parent log identifier (null is allowed). |
| **Loglevel** | **string** | Required | The log level. |
| **Logstatus** | **string** | Required | The log status. |
| **Sourcerecordtype** | **string** | Optional | The source record type. |
| **Sourceprimaryidtype** | **string** | Optional | The source primary ID type. |
| **Sourceprimaryidvalue** | **string** | Optional | The source primary ID value. |
| **Targetrecordtype** | **string** | Optional | The target record type. |
| **Targetrecordaction** | **string** | Optional | The target record action. |
| **Targetprimaryidtype** | **string** | Optional | The target primary ID type. |
| **Targetprimaryidvalue** | **string** | Optional | The target primary ID value. |
| **Message** | **string** | Optional | The log message. |
| **Messagetype** | **string** | Optional | The message type. |
| **Timestamp** | **string** | Required | The timestamp of the log record. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ExternalLogRecord(
    logid: 0L,  // required — The unique log identifier.
    parentlogid: 0L,  // optional — The parent log identifier (null is allowed).
    loglevel: "...",  // required — The log level.
    logstatus: "...",  // required — The log status.
    sourcerecordtype: "...",  // optional — The source record type.
    sourceprimaryidtype: "...",  // optional — The source primary ID type.
    sourceprimaryidvalue: "...",  // optional — The source primary ID value.
    targetrecordtype: "...",  // optional — The target record type.
    targetrecordaction: "...",  // optional — The target record action.
    targetprimaryidtype: "...",  // optional — The target primary ID type.
    targetprimaryidvalue: "...",  // optional — The target primary ID value.
    message: "...",  // optional — The log message.
    messagetype: "...",  // optional — The message type.
    timestamp: "..."  // required — The timestamp of the log record.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalLogRecord>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

