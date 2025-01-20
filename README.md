# Zeptonet

An experimental software-defined mesh virtual private network.

## Control Plane

A Rails application with:

- GitHub OAuth authentication.
- A RESTful API to manage machines.
- OAuth2 authentication for the API using Doorkeeper, supporting:
  - Authorization code and client credentials flows.
  - PKCE (Proof Key for Code Exchange) for public clients (like the CLI).

## CLI on the host machines

A Go application with:

- Cobra framework.
- GitHub OAuth authentication for login.
- Communication with the control plane API using OAuth2 PKCE authentication.
- Machine registration via the API.
- WireGuard configuration using the wireguard-go library, as directed by the control plane via the API.
- Heartbeat to the control plane via the API.
