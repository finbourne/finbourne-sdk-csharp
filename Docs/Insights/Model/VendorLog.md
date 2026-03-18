# Finbourne.Sdk.Insights.Model.VendorLog

Holds logged information about a request made to an external vendor.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The identifier of a log entry. |
| **Provider** | **string** | Required | The provider or service name. |
| **Timestamp** | **DateTimeOffset** | Required | Timestamp of when the log was generated. |
| **Type** | **string** | Required | Type of log. Possible values: HttpResponse. |
| **DestinationUrl** | **string** | Required | The destination URL of the task. |
| **Operation** | **string** | Required | The operation performed. Possible values: Evaluate. |
| **Outcome** | **string** | Required | The outcome of the operation. Possible values: Success, Failure. |
| **Duration** | **decimal** | Required | The duration of the operation in ms. |
| **HttpStatusCode** | **int** | Required | The status code of the operation. |
| **UserId** | **string** | Required | The user that made the request to LUSID. |
| **RequestId** | **string** | Required | The ID of the request to LUSID. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new VendorLog(
    id: "...",  // required — The identifier of a log entry.
    provider: "...",  // required — The provider or service name.
    timestamp: DateTimeOffset.Now,  // required — Timestamp of when the log was generated.
    type: "...",  // required — Type of log. Possible values: HttpResponse.
    destinationUrl: "...",  // required — The destination URL of the task.
    operation: "...",  // required — The operation performed. Possible values: Evaluate.
    outcome: "...",  // required — The outcome of the operation. Possible values: Success, Failure.
    duration: 0.0d,  // required — The duration of the operation in ms.
    httpStatusCode: 0,  // required — The status code of the operation.
    userId: "...",  // required — The user that made the request to LUSID.
    requestId: "...",  // required — The ID of the request to LUSID.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorLog>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

