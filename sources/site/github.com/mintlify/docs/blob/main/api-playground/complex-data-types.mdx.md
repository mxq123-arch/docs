# Source: https://github.com/mintlify/docs/blob/main/api-playground/complex-data-types.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# complex-data-types.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/api-playground/complex-data-types.mdx)

History

100 lines (83 loc) · 3.92 KB

 main

/

# complex-data-types.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

100 lines (83 loc) · 3.92 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/api-playground/complex-data-types.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Complex data types</td></tr><tr><th>description</th><td>Describe APIs with flexible schemas using oneOf, anyOf, and allOf keywords for optional properties, polymorphism, and multiple data formats.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">oneOf</div></th><th><div dir="auto">anyOf</div></th><th><div dir="auto">allOf</div></th><th><div dir="auto">schema composition</div></th><th><div dir="auto">polymorphic schemas</div></th></tr></tbody></table></td></tr></tbody></table>

When your API accepts multiple data formats, has conditional fields, or uses inheritance patterns, OpenAPI's schema composition keywords help you document these flexible structures. Using `oneOf`, `anyOf`, and `allOf`, you can describe APIs that handle different input types or combine multiple schemas into comprehensive data models.

## `oneOf`, `anyOf`, `allOf` keywords

For complex data types, OpenAPI provides keywords for combining schemas:

- `allOf`: Combines multiple schemas (like merging objects or extending a base schema). Functions like an `and` operator.
- `anyOf`: Accepts data matching any of the provided schemas. Functions like an `or` operator.
- `oneOf`: Accepts data matching exactly one of the provided schemas. Functions like an `exclusive-or` operator.

Mintlify treats `oneOf` and `anyOf` identically since the practical difference rarely affects using the API.

For detailed specifications of these keywords see the [OpenAPI documentation](https://swagger.io/docs/specification/data-models/oneof-anyof-allof-not/).

The `not` keyword is currently unsupported.

### Combining schemas with `allOf`

When you use `allOf`, Mintlify performs some preprocessing on your OpenAPI document to display complex combinations in a readable way. For example, when you combine two object schemas with `allOf`, Mintlify combines the properties of both into a single object. This becomes especially useful when you use OpenAPI's reusable [components](https://swagger.io/docs/specification/components/).

```yaml
org_with_users:
  allOf:
    - $ref: '#/components/schemas/Org'
    - type: object
      properties:
        users:
          type: array
          description: An array containing all users in the organization
# ...
components:
  schemas:
    Org:
      type: object
      properties:
        id:
          type: string
          description: The ID of the organization
```

The ID of the organization An array containing all users in the organization

### `any` and `undefined` types

Fields typed as `any` or `undefined` render the same way as `oneOf` schemas with a picker that lets users select a concrete shape before sending a request. This allows the API playground to present a meaningful input even when the schema doesn't constrain the value to a single type.

### Providing options with `oneOf` and `anyOf`

When you use `oneOf` or `anyOf`, the options display in a tabbed container. Specify a `title` field in each subschema to give your options names. For example, here's how you might display two different types of delivery addresses:

```yaml
delivery_address:
  oneOf:
    - title: StreetAddress
      type: object
      properties:
        address_line_1:
          type: string
          description: The street address of the recipient
        # ...
    - title: POBox
      type: object
      properties:
        box_number:
          type: string
          description: The number of the PO Box
        # ...
```

The street address of the residence The number of the PO Box