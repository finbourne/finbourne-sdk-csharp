# Finbourne.Sdk.Insights.Model.Response

DTO of Finbourne.AspNetCore.Http.TrackingEntry.ResponseInformation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Headers** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | Optional | The headers |
| **ContentLength** | **long?** | Optional | The actual length of the body, which may be larger than the data recorded in Finbourne.Insights.WebApi.Dtos.Response.Body (e.g. if actual Body is large, or not convertible to a string) |
| **ContentType** | **string** | Optional | The content type |
| **Body** | **string** | Optional | The recorded content. |
| **BodyWasTruncated** | **bool** | Optional | Determines if the recorded body was truncated. |
| **StatusCode** | **int** | Optional | Http Status Code of the request. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new Response(
    headers: ,  // optional — The headers
    contentLength: 0L,  // optional — The actual length of the body, which may be larger than the data recorded in Finbourne.Insights.WebApi.Dtos.Response.Body (e.g. if actual Body is large, or not convertible to a string)
    contentType: "...",  // optional — The content type
    body: "...",  // optional — The recorded content.
    bodyWasTruncated: true,  // optional — Determines if the recorded body was truncated.
    statusCode: 0,  // optional — Http Status Code of the request.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Response>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

