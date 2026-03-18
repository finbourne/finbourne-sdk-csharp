# Finbourne.Sdk.Insights.Model.AccessEvaluationLog

Holds logged information about an access check performed on an API.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Timestamp** | **DateTimeOffset** | Required | The timestamp of the access evaluation. |
| **Application** | **string** | Required | The name of the application that the request was made from. |
| **Id** | **string** | Required | The ID of the access evaluation. |
| **RequestId** | **string** | Optional | The identifier of the request. |
| **SessionId** | **string** | Optional | The identifier of the session that the request was made in. |
| **User** | **string** | Required | The user who made the request. |
| **UserType** | **string** | Optional | The type of the user who made the request. |
| **Duration** | **decimal** | Required | The duration of the access evaluation. |
| **Result** | **string** | Optional | The result of the access evaluation. |
| **AuthoritativeRoleId** | **string** | Optional | The role that matched the access evaluation to provide a result. |
| **AuthoritativePolicyId** | **string** | Optional | The policy that matched the access evaluation to provide a result. |
| **AuthoritativeSelector** | **string** | Optional | The selector that matched the access evaluation to provide a result. |
| **ResourceType** | **string** | Optional | The type of the resource that the access evaluation is for. |
| **Action** | **string** | Optional | The action key of the access evaluation. |
| **Resource** | **Dictionary&lt;string, string&gt;** | Optional | The ID of the resource that the access evaluation is for. If the ResourceID could not be converted to a dictionary, it will return a single-value dictionary with the key \&quot;resourceId\&quot;. |
| **ResourceFromEffectiveDate** | **string** | Optional | The From effective date of the resource. |
| **ResourceToEffectiveDate** | **string** | Optional | The To effective date of the resource. |
| **ResourceFromAsAt** | **string** | Optional | The From AsAt date of the resource. |
| **ResourceToAsAt** | **string** | Optional | The To AsAt date of the resource. |
| **AccessExecutionTime** | **string** | Optional | The execution time of the entitlement. |
| **AccessAsAtTime** | **string** | Optional | The AsAt time of the entitlement. |
| **RequiredLicencePolicyId** | **string** | Optional | ID of the required licence policy. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AccessEvaluationLog(
    timestamp: DateTimeOffset.Now,  // required — The timestamp of the access evaluation.
    application: "...",  // required — The name of the application that the request was made from.
    id: "...",  // required — The ID of the access evaluation.
    requestId: "...",  // optional — The identifier of the request.
    sessionId: "...",  // optional — The identifier of the session that the request was made in.
    user: "...",  // required — The user who made the request.
    userType: "...",  // optional — The type of the user who made the request.
    duration: 0.0d,  // required — The duration of the access evaluation.
    result: "...",  // optional — The result of the access evaluation.
    authoritativeRoleId: "...",  // optional — The role that matched the access evaluation to provide a result.
    authoritativePolicyId: "...",  // optional — The policy that matched the access evaluation to provide a result.
    authoritativeSelector: "...",  // optional — The selector that matched the access evaluation to provide a result.
    resourceType: "...",  // optional — The type of the resource that the access evaluation is for.
    action: "...",  // optional — The action key of the access evaluation.
    resource: ,  // optional — The ID of the resource that the access evaluation is for. If the ResourceID could not be converted to a dictionary, it will return a single-value dictionary with the key \&quot;resourceId\&quot;.
    resourceFromEffectiveDate: "...",  // optional — The From effective date of the resource.
    resourceToEffectiveDate: "...",  // optional — The To effective date of the resource.
    resourceFromAsAt: "...",  // optional — The From AsAt date of the resource.
    resourceToAsAt: "...",  // optional — The To AsAt date of the resource.
    accessExecutionTime: "...",  // optional — The execution time of the entitlement.
    accessAsAtTime: "...",  // optional — The AsAt time of the entitlement.
    requiredLicencePolicyId: "...",  // optional — ID of the required licence policy.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessEvaluationLog>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

