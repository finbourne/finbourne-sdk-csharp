# Finbourne.Sdk.Horizon.Model.FailedDeliveryResponse

A batch's failed deliveries returned by the list endpoint, aggregated to one row per batch. Finbourne.Horizon.Integrations.Web.Dto.Integrations.TradePublicationFramework.Response.FailedDeliveryResponse.FailedCount is the number of failed deliveries in the batch and Finbourne.Horizon.Integrations.Web.Dto.Integrations.TradePublicationFramework.Response.FailedDeliveryResponse.FailureReason is the comma-separated set of their failure reasons.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BatchReferenceId** | **string** | Required | *No description available.* |
| **RunId** | **Guid** | Required | *No description available.* |
| **RunStartTime** | **DateTimeOffset** | Required | *No description available.* |
| **FailedCount** | **int** | Required | *No description available.* |
| **FailureReason** | **string** | Required | *No description available.* |
| **LastAttemptAt** | **DateTimeOffset** | Required | *No description available.* |
| **AttemptCount** | **int** | Required | *No description available.* |
| **Resolved** | **bool** | Required | *No description available.* |
| **ResolvedAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **ResolutionReason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new FailedDeliveryResponse(
    batchReferenceId: "...",  // required
    runId: "...",  // required
    runStartTime: DateTimeOffset.Now,  // required
    failedCount: 0,  // required
    failureReason: "...",  // required
    lastAttemptAt: DateTimeOffset.Now,  // required
    attemptCount: 0,  // required
    resolved: true,  // required
    resolvedAt: DateTimeOffset.Now,  // optional
    resolutionReason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FailedDeliveryResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

