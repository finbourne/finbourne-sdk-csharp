# Finbourne.Sdk.Luminesce.Model.CaseStatementItem

Information about a case statement. A typical case statement would look like: CASE WHEN Field {Filter} Source THEN Target For example: CASE WHEN 'currency' = 'USD' THEN 'US' Here the Field is 'currency', the Source is 'USD', the Filter is '=', and the Target is 'US'
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Filter** | **string** | Required | The operator in the case statement SQL expression |
| **Source** | **string** | Required | The expression that is on the LHS of the operator A typical case statement would look like: CASE Field {Filter} Source THEN Target |
| **Target** | **string** | Required | The expression that is on the RHS of the operator A typical case statement would look like: CASE Field {Filter} Source THEN Target |
| **IsTargetNonLiteral** | **bool** | Optional | The Target can be a literal value or a non literal (field) and hence will be interpreted differently. This can be determined from the UI and passed down as a true / false |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CaseStatementItem(
    filter: "...",  // required — The operator in the case statement SQL expression
    source: "...",  // required — The expression that is on the LHS of the operator A typical case statement would look like: CASE Field {Filter} Source THEN Target
    target: "...",  // required — The expression that is on the RHS of the operator A typical case statement would look like: CASE Field {Filter} Source THEN Target
    isTargetNonLiteral: true  // optional — The Target can be a literal value or a non literal (field) and hence will be interpreted differently. This can be determined from the UI and passed down as a true / false
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CaseStatementItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

