# Finbourne.Sdk.Lusid.Model.SecurityOfferElection

Election for events that result in cash via a merger or acquisition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key associated to this election. |
| **IsChosen** | **bool** | Optional | Is this the election that has been explicitly chosen from multiple options. |
| **IsDefault** | **bool** | Optional | Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided. |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SecurityOfferElection(
    electionKey: "...",  // required — Unique key associated to this election.
    isChosen: true,  // optional — Is this the election that has been explicitly chosen from multiple options.
    isDefault: true,  // optional — Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided.
    unitsRatio: new UnitsRatio(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SecurityOfferElection>(json);
```

- [UnitsRatio](UnitsRatio.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

