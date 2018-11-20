# Bittrex Developers
URL: [https://bittrex.github.io](https://bittrex.github.io)


## Installation
1. Install Jekyll
    - For windows users, follow the instructions [here](https://jekyllrb.com/docs/installation/windows/#installing-jekyll)
1. Ensure you have [Node.js](https://nodejs.org/en/download/) installed. Aim for these versions:
    - `node >= 8`
    - `npm >= 5`
1. Install dependencies by running the following:
    - `bundle install`
    - `npm install`
1. You should be ready to go!

## Development
The docs are built using Jekyll, which serves the generated HTML. We use spectacle to generate the more sophisticated HTML, CSS and JS for the API reference pages.

To get started, first try building the API reference pages and then serve them, like so:
1. `npm run build` - builds necessary assets
1. `npm run serve` - starts server
1. Navigate your browser to `http://localhost:4000/` 

In active development, we use npm-watch to watch for changes. Either:
- Run `npm run dev` to serve and watch in one process
or:
1. In one process: `npm run watch` - watch the build directories
1. In a _separate_ process: `npm run serve`

**Note**: _Errors like `Liquid Exception: Could not locate the included file 'assets/index.html'` in the jekyll process as the spectacle docs get rebuilt are normal._

**Note**: _You can also just watch specific builds by specifying which build step to watch like: `npm run watch [watch script]`_

## Updating the Docs with a new API Spec
In order to update the docs site with a new version of the API spec, all you have to do is build spectacle with the new spec file.
For example, to rebuild the v3 docs:
1. Place the new API spec JSON file at `_data/api-spec-v3.json` (overwrite the current file)
1. Rebuild the docs `npm run build`

**Note**: _You can test the changes by starting jekyll: `npm run serve`_



## Custom Swagger/OpenAPI Implementations
The API reference pages use a modified version of the OpenAPI (aka Swagger) API specification version 2. Documentation for the specification can be found [here](https://swagger.io/specification/v2/). Over time, we should keep the API spec JSON files as close to the spec as we can, any custom properties (prefixed with `x-`) and their use cases should be documented here.

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
