# Finbourne.Sdk.Lusid.Model.ExternalRecDefinitionDetails

A definition reconciling relational data on both sides, driven by a single External matching ruleset.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MatchingRulesetId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LeftFilter** | **string** | Optional | Optional filter over the left dataset&#39;s rows, in the dataset&#39;s own grammar, e.g. \&quot;Values[custodian] eq &#39;something&#39;\&quot;. |
| **RightFilter** | **string** | Optional | Optional filter over the right dataset&#39;s rows, in the dataset&#39;s own grammar. |
| **DefinitionType** | **string** | Required | What this definition reconciles, and so which shape of details it carries. Available values: PortfolioContents, LusidEntity, External. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalRecDefinitionDetails(
    matchingRulesetId: new ResourceId(...),  // required
    leftFilter: "...",  // optional — Optional filter over the left dataset&#39;s rows, in the dataset&#39;s own grammar, e.g. \&quot;Values[custodian] eq &#39;something&#39;\&quot;.
    rightFilter: "...",  // optional — Optional filter over the right dataset&#39;s rows, in the dataset&#39;s own grammar.
    definitionType: "..."  // required — What this definition reconciles, and so which shape of details it carries. Available values: PortfolioContents, LusidEntity, External.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalRecDefinitionDetails>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

