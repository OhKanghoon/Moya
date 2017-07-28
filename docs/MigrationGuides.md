# Migration Guides

This project follows [Semantic Versioning](http://semver.org).

Please follow the appropriate guide below when **upgrading to a new major version** of Moya (e.g. 8.0 -> 9.0).

## Upgrade from 8.x to 9.x

- Move the `parameters` and `parameterEncoding` to the `task` computed property by using the case `.requestParameters(parameters:,encoding:)`
- Replace the task type `.request` with either `.requestPlain` (if you have no parameters) or `.requestParameters(parameters:,encoding:)`
- There's no `parameters` and `parameterEncoding` on Endpoints any more (e.g. `addingParameters()`), use the new `task` property instead
- To send URL encoded parameters AND body parameters, you can now use the task type `.requestCompositeParameters(bodyParameters:,bodyEncoding:,urlParameters:)`
- Simplify occurrences of task type `.download(.request(destination))` to `.downloadDestination(destination)`
- Simplify occurrences of task type `.upload(.file(url))` to `.uploadFile(url)`
- Simplify occurrences of task type `.upload(.multipart(data))` to `.uploadMultipart(data)`