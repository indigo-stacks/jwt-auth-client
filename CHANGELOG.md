# Changelog

## 3.0.0 (2026-10-28)

### Breaking changes

- Remove the Pulse dependency. The package no longer links Pulse in any build configuration.
- Require http-request-client 2.0, which replaces `Pulse.URLSessionProtocol` with its own `HTTPTransport` protocol. `URLSession` conforms to it.
- `JWTAuthClient.send` and `JWTAuthClient.sendAuthenticated` take `urlSession: HTTPTransport` instead of `URLSessionProtocol`. Argument labels and defaults do not change.

### Migration

- Replace `URLSessionProtocol` with `HTTPTransport` in your code.
- To keep Pulse network logging, add Pulse to your app (for example in Debug only) and declare `extension URLSessionProxy: @retroactive HTTPTransport {}`.

See the README section "Migrating from 2.x to 3.0".

## 2.1.0

- Use `URLSessionProtocol` (from Pulse) in the public API instead of `URLSession`.
