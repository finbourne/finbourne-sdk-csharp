# Finbourne.Sdk.Identity.Model.LogRequest

Represents a LogRequest resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IpChain** | [List&lt;LogIpChainEntry&gt;](LogIpChainEntry.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogRequest(
    ipChain: new List<LogIpChainEntry>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogRequest>(json);
```


## Related Models

- [LogIpChainEntry](LogIpChainEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

