# Finbourne.Sdk.Horizon.Model.ExternalLogRecord

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Logid** | **long** | Required | *No description available.* |
| **Parentlogid** | **long?** | Optional | *No description available.* |
| **Loglevel** | **string** | Required | *No description available.* |
| **Logstatus** | **string** | Required | *No description available.* |
| **Sourcerecordtype** | **string** | Optional | *No description available.* |
| **Sourceprimaryidtype** | **string** | Optional | *No description available.* |
| **Sourceprimaryidvalue** | **string** | Optional | *No description available.* |
| **Targetrecordtype** | **string** | Optional | *No description available.* |
| **Targetrecordaction** | **string** | Optional | *No description available.* |
| **Targetprimaryidtype** | **string** | Optional | *No description available.* |
| **Targetprimaryidvalue** | **string** | Optional | *No description available.* |
| **Message** | **string** | Optional | *No description available.* |
| **Messagetype** | **string** | Optional | *No description available.* |
| **Timestamp** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ExternalLogRecord(
    logid: 0L,  // required
    parentlogid: 0L,  // optional
    loglevel: "...",  // required
    logstatus: "...",  // required
    sourcerecordtype: "...",  // optional
    sourceprimaryidtype: "...",  // optional
    sourceprimaryidvalue: "...",  // optional
    targetrecordtype: "...",  // optional
    targetrecordaction: "...",  // optional
    targetprimaryidtype: "...",  // optional
    targetprimaryidvalue: "...",  // optional
    message: "...",  // optional
    messagetype: "...",  // optional
    timestamp: "..."  // required
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

