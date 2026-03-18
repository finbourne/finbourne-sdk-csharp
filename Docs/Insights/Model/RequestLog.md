# Finbourne.Sdk.Insights.Model.RequestLog

Holds logged information about a request performed on an API.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Timestamp** | **DateTimeOffset** | Required | The timestamp of the request. |
| **Application** | **string** | Required | The name of the application that the request was made to. |
| **Id** | **string** | Required | The identifier of the request. |
| **SessionId** | **string** | Optional | The identifier of the session that the request was made in. |
| **Verb** | **string** | Required | The HTTP verb of the request. |
| **Url** | **string** | Required | The URL of the request. |
| **Domain** | **string** | Optional | The domain of the request. |
| **User** | **string** | Required | The user who made the request. |
| **UserType** | **string** | Optional | The type of the user who made the request. |
| **Operation** | **string** | Optional | The API operation invoked by the request. |
| **Outcome** | **string** | Required | The outcome of the request: Completed, Errored or Failed. |
| **Duration** | **decimal** | Required | The duration of the request in milliseconds. |
| **HttpStatusCode** | **int** | Required | The status code of the request. |
| **ErrorCode** | **string** | Optional | Error code, if the request had a failure or error. |
| **SdkLanguage** | **string** | Optional | The language of the SDK used. |
| **SdkVersion** | **string** | Optional | The version of the SDK used. |
| **SourceApplication** | **string** | Optional | The name of the application that made the request. |
| **CorrelationId** | **List&lt;string&gt;** | Optional | The chain of requestIds preceding this request |
| **ImpersonatingUser** | **string** | Optional | The impersonating user. Only present if the request is an impersonated one |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new RequestLog(
    timestamp: DateTimeOffset.Now,  // required — The timestamp of the request.
    application: "...",  // required — The name of the application that the request was made to.
    id: "...",  // required — The identifier of the request.
    sessionId: "...",  // optional — The identifier of the session that the request was made in.
    verb: "...",  // required — The HTTP verb of the request.
    url: "...",  // required — The URL of the request.
    domain: "...",  // optional — The domain of the request.
    user: "...",  // required — The user who made the request.
    userType: "...",  // optional — The type of the user who made the request.
    operation: "...",  // optional — The API operation invoked by the request.
    outcome: "...",  // required — The outcome of the request: Completed, Errored or Failed.
    duration: 0.0d,  // required — The duration of the request in milliseconds.
    httpStatusCode: 0,  // required — The status code of the request.
    errorCode: "...",  // optional — Error code, if the request had a failure or error.
    sdkLanguage: "...",  // optional — The language of the SDK used.
    sdkVersion: "...",  // optional — The version of the SDK used.
    sourceApplication: "...",  // optional — The name of the application that made the request.
    correlationId: ,  // optional — The chain of requestIds preceding this request
    impersonatingUser: "...",  // optional — The impersonating user. Only present if the request is an impersonated one
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestLog>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

