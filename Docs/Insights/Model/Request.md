# Finbourne.Sdk.Insights.Model.Request

DTO of Finbourne.AspNetCore.Http.TrackingEntry.RequestInformation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Headers** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | Optional | The headers |
| **ContentLength** | **long?** | Optional | The actual length of the body, which may be larger than the data recorded in Finbourne.Insights.WebApi.Dtos.Request.Body (e.g. if actual Body is large, or not convertible to a string) |
| **ContentType** | **string** | Optional | The content type |
| **Body** | **string** | Optional | The recorded content. |
| **BodyWasTruncated** | **bool** | Optional | Determines if the recorded body was truncated. |
| **Method** | **string** | Optional | Method called by the request |
| **Url** | **string** | Optional | URL of the request |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new Request(
    headers: ,  // optional — The headers
    contentLength: 0L,  // optional — The actual length of the body, which may be larger than the data recorded in Finbourne.Insights.WebApi.Dtos.Request.Body (e.g. if actual Body is large, or not convertible to a string)
    contentType: "...",  // optional — The content type
    body: "...",  // optional — The recorded content.
    bodyWasTruncated: true,  // optional — Determines if the recorded body was truncated.
    method: "...",  // optional — Method called by the request
    url: "...",  // optional — URL of the request
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Request>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

