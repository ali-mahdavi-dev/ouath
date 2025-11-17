# OAuth 2.0 & OpenID Connect

This repository contains resources and documentation related to OAuth 2.0 and OpenID Connect protocols.

## Contents

- **oauth.xmind**: Mind Map for OAuth 2.0
- **oauth 2.0.svg**: SVG diagram and illustration for OAuth 2.0

### OAuth 2.0 Diagram

![OAuth 2.0 Flow Diagram](oauth%202.0.svg)

## OAuth 2.0

OAuth 2.0 is a standard protocol for authorization that enables applications to obtain limited access to user resources on an HTTP service. It is widely used for API access and allows users to grant third-party applications access to their resources without sharing their credentials.

### Key Features

- **High Security**: Uses access tokens instead of user credentials
- **Flexibility**: Supports multiple grant types for different use cases
- **Industry Standard**: Widely adopted and standardized protocol

### Grant Types

OAuth 2.0 supports several grant types:

- **Authorization Code**: For server-side applications (most secure)
- **Implicit**: For client-side applications (deprecated, use Authorization Code with PKCE instead)
- **Resource Owner Password Credentials**: For trusted applications
- **Client Credentials**: For machine-to-machine communication

### OAuth 2.0 Flow

The typical OAuth 2.0 authorization flow involves:

1. **Client** requests authorization from the **Resource Owner**
2. **Resource Owner** grants authorization
3. **Client** receives an authorization grant
4. **Client** requests an access token from the **Authorization Server**
5. **Authorization Server** validates the grant and issues an access token
6. **Client** uses the access token to access protected resources from the **Resource Server**

## OpenID Connect (OIDC)

OpenID Connect is an authentication layer built on top of OAuth 2.0. While OAuth 2.0 focuses on authorization (what you can do), OpenID Connect adds authentication (who you are) capabilities.

### Key Features

- **Identity Layer**: Adds identity verification to OAuth 2.0
- **ID Tokens**: Provides ID tokens (JWT) containing user identity information
- **UserInfo Endpoint**: Standardized endpoint to retrieve user profile information
- **Standard Claims**: Defines standard claims for user attributes

### OpenID Connect vs OAuth 2.0

| Feature        | OAuth 2.0                | OpenID Connect                     |
| -------------- | ------------------------ | ---------------------------------- |
| **Purpose**    | Authorization            | Authentication + Authorization     |
| **Token Type** | Access Token             | Access Token + ID Token            |
| **User Info**  | Not standardized         | Standardized via UserInfo endpoint |
| **Identity**   | No identity verification | Identity verification included     |

### OpenID Connect Flow

The OpenID Connect flow extends OAuth 2.0:

1. **Client** initiates authentication request with `openid` scope
2. **Authorization Server** authenticates the user
3. **Authorization Server** returns both **Access Token** and **ID Token** (JWT)
4. **Client** can use the **ID Token** to identify the user
5. **Client** can optionally call the **UserInfo Endpoint** with the access token to get additional user information

### ID Token

The ID Token is a JWT (JSON Web Token) that contains:

- **iss** (issuer): The authorization server that issued the token
- **sub** (subject): Unique identifier for the user
- **aud** (audience): The client ID this token is intended for
- **exp** (expiration): Token expiration time
- **iat** (issued at): Time when the token was issued
- **nonce**: Random value to prevent replay attacks
- **auth_time**: Time when authentication occurred

### Scopes

OpenID Connect defines several scopes:

- **openid**: Required for OpenID Connect authentication
- **profile**: Access to user's profile information
- **email**: Access to user's email address
- **address**: Access to user's address
- **phone**: Access to user's phone number

## Resources

### OAuth 2.0

- [RFC 6749 - OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749)
- [OAuth 2.0 Documentation](https://oauth.net/2/)
- [OAuth 2.0 Simplified](https://www.oauth.com/)

### OpenID Connect

- [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html)
- [OpenID Connect Documentation](https://openid.net/connect/)
- [OpenID Connect Explained](https://openid.net/developers/how-connect-works/)

## License

This project is created for educational and documentation purposes.
