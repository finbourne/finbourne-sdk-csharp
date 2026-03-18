# Finbourne.Sdk.Horizon.Model.JSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SchemaVersion** | **string** | Optional | *No description available.* |
| **Valid** | **bool?** | Optional | *No description available.* |
| **Reference** | **string** | Optional | *No description available.* |
| **Ref** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **RecursiveReference** | **string** | Optional | *No description available.* |
| **RecursiveAnchor** | **bool?** | Optional | *No description available.* |
| **Id** | **string** | Optional | *No description available.* |
| **Anchor** | **string** | Optional | *No description available.* |
| **Type** | **JSchemaType** | Optional | *No description available.* |
| **Default** | **Object** | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **Items** | [List&lt;JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **ItemsPositionValidation** | **bool** | Required | *No description available.* |
| **Required** | **List&lt;string&gt;** | Required | *No description available.* *(read-only)* |
| **AllOf** | [List&lt;JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **AnyOf** | [List&lt;JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **OneOf** | [List&lt;JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **If** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **Then** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **Else** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **Not** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **Contains** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **PropertyNames** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **Enum** | **List&lt;Object&gt;** | Required | *No description available.* *(read-only)* |
| **Const** | **Object** | Optional | *No description available.* |
| **UniqueItems** | **bool** | Required | *No description available.* |
| **MinimumLength** | **long?** | Optional | *No description available.* |
| **MaximumLength** | **long?** | Optional | *No description available.* |
| **ExclusiveMinimum** | **bool** | Required | *No description available.* |
| **ExclusiveMaximum** | **bool** | Required | *No description available.* |
| **MinimumItems** | **long?** | Optional | *No description available.* |
| **MaximumItems** | **long?** | Optional | *No description available.* |
| **MinimumProperties** | **long?** | Optional | *No description available.* |
| **MaximumProperties** | **long?** | Optional | *No description available.* |
| **MinimumContains** | **long?** | Optional | *No description available.* |
| **MaximumContains** | **long?** | Optional | *No description available.* |
| **ContentEncoding** | **string** | Optional | *No description available.* |
| **ContentMediaType** | **string** | Optional | *No description available.* |
| **WriteOnly** | **bool?** | Optional | *No description available.* |
| **ReadOnly** | **bool?** | Optional | *No description available.* |
| **ExtensionData** | **Dictionary&lt;string, Object&gt;** | Required | *No description available.* *(read-only)* |
| **Title** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **MultipleOf** | **decimal?** | Optional | *No description available.* |
| **Pattern** | **string** | Optional | *No description available.* |
| **Dependencies** | **Dictionary&lt;string, Object&gt;** | Required | *No description available.* *(read-only)* |
| **DependentRequired** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | Required | *No description available.* *(read-only)* |
| **DependentSchemas** | [Dictionary&lt;string, JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **PatternProperties** | [Dictionary&lt;string, JSchema&gt;](JSchema.md) | Required | *No description available.* *(read-only)* |
| **AdditionalProperties** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **AllowAdditionalProperties** | **bool** | Required | *No description available.* |
| **AllowAdditionalPropertiesSpecified** | **bool** | Required | *No description available.* |
| **UnevaluatedProperties** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **AllowUnevaluatedProperties** | **bool?** | Optional | *No description available.* |
| **AdditionalItems** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **AllowAdditionalItems** | **bool** | Required | *No description available.* |
| **AllowAdditionalItemsSpecified** | **bool** | Required | *No description available.* |
| **UnevaluatedItems** | [JSchema](JSchema.md) | Optional | *No description available.* |
| **AllowUnevaluatedItems** | **bool?** | Optional | *No description available.* |
| **Format** | **string** | Optional | *No description available.* |
| **Validators** | **List&lt;Object&gt;** | Required | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new JSchema(
    schemaVersion: "...",  // optional
    valid: true,  // optional
    reference: "...",  // optional
    varRef: new JSchema(...),  // optional
    recursiveReference: "...",  // optional
    recursiveAnchor: true,  // optional
    id: "...",  // optional
    anchor: "...",  // optional
    type: ,  // optional
    varDefault: ,  // optional
    properties: new JSchema(...),  // required
    items: new List<JSchema>(),  // required
    itemsPositionValidation: true,  // required
    required: ,  // required
    allOf: new List<JSchema>(),  // required
    anyOf: new List<JSchema>(),  // required
    oneOf: new List<JSchema>(),  // required
    varIf: new JSchema(...),  // optional
    then: new JSchema(...),  // optional
    varElse: new JSchema(...),  // optional
    not: new JSchema(...),  // optional
    contains: new JSchema(...),  // optional
    propertyNames: new JSchema(...),  // optional
    varEnum: ,  // required
    varConst: ,  // optional
    uniqueItems: true,  // required
    minimumLength: 0L,  // optional
    maximumLength: 0L,  // optional
    exclusiveMinimum: true,  // required
    exclusiveMaximum: true,  // required
    minimumItems: 0L,  // optional
    maximumItems: 0L,  // optional
    minimumProperties: 0L,  // optional
    maximumProperties: 0L,  // optional
    minimumContains: 0L,  // optional
    maximumContains: 0L,  // optional
    contentEncoding: "...",  // optional
    contentMediaType: "...",  // optional
    writeOnly: true,  // optional
    readOnly: true,  // optional
    extensionData: ,  // required
    title: "...",  // optional
    description: "...",  // optional
    multipleOf: 0.0d,  // optional
    pattern: "...",  // optional
    dependencies: ,  // required
    dependentRequired: ,  // required
    dependentSchemas: new JSchema(...),  // required
    patternProperties: new JSchema(...),  // required
    additionalProperties: new JSchema(...),  // optional
    allowAdditionalProperties: true,  // required
    allowAdditionalPropertiesSpecified: true,  // required
    unevaluatedProperties: new JSchema(...),  // optional
    allowUnevaluatedProperties: true,  // optional
    additionalItems: new JSchema(...),  // optional
    allowAdditionalItems: true,  // required
    allowAdditionalItemsSpecified: true,  // required
    unevaluatedItems: new JSchema(...),  // optional
    allowUnevaluatedItems: true,  // optional
    format: "...",  // optional
    validators:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<JSchema>(json);
```

- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)
- [JSchema](JSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

