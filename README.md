
## Fork Info

* https://github.com/ranzwertig/php-json-schema fork adds support full iso-8601 for format date-time
* https://github.com/shrm-org/php-json-schema fork:
  1. fixes [json-schema patterns do NOT have delimiters](https://github.com/hasbridge/php-json-schema/pull/5)
  2. adds support for required array at object level

---

This library provides JSON schema validation using the schema found at http://json-schema.org.
Note that it is not yet feature complete, but does support basic validation. The JSON schema
draft can be found at http://tools.ietf.org/html/draft-zyp-json-schema-03

## Requirements
- PHP 5.3 or greater (requires namespace and closure support)

## Usage

    $someJson = '{"foo":"bar"}';
    $jsonObject = json_decode($someJson);

    $validator = new JsonValidator('/path/to/yourschema.json');

    $validator->validate($jsonObject);


## Supported Types

Types may be defined as either a single string type name, or an array of allowable
type names.

- string
- number
- integer
- boolean
- object
- array
- null
- any

## Supported Definitions

Not all definitions are yet supported, but here is a list of those which are:

- properties (object)
- additionalProperties (object)
- required (all)
- pattern (string)
- minLength (string)
- maxLength (string)
- format (string, number, integer)
- minimum (number, integer)
- maximum (number, integer)
- exclusiveMinimum (number, integer)
- exclusiveMaximum (number, integer)
- divisibleBy (number, integer)
- enum (array)
- minItems (array)
- maxItems (array)
- uniqueItems (array)
- items (array)
- disallow (all)

The following definitions are not yet supported:

- patternProperties
- dependencies
- extends
- id
- $ref
- $schema
