# Bittrex Developers

## Installation
_(Instructions coming soon...)_

## Development
_(Instructions coming soon...)_

## Updating the Docs with a new API Spec
_(Instructions coming soon...)_

## Custom Swagger/OpenAPI Implementations
The API reference pages use a modified version of the OpenAPI (aka Swagger) API specification version 2. Documentation for the specification can be found [here](https://swagger.io/specification/v2/). Over time, we should keep the API spec JSON files as close to the spec as we can.

### `x-btx-methods`
A section of the JSON API spec that accommodates Websocket methods. A sibling of the [Paths Object](https://swagger.io/specification/v2/#pathsObject), though each property key maps to 
an `x-btx-method`

### `x-btx-method`
An individual Websocket method, similar in shape to an [Operation object](https://swagger.io/specification/v2/#operationObject)

### `x-btx-request-example`
An additional property (type: `string`) allowed in the [Operation object](https://swagger.io/specification/v2/#operationObject). Used to show an example request url.

### Parameters object
Base definition can be found here: [Parameter object](https://swagger.io/specification/v2/#parameterObject)
- `in` is no longer required