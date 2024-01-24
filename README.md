# Spring Security: SSO-OAuth-JWT-Keycloak
 
It consists of 3 modules:

1. Basic Spring security with DaoAuthProvider (https://github.com/vikramshanbogar/Spring-Security--SSO-OAuth-JWT-Keycloak/tree/main/SpringSecurity-SpringBoot)
2. OAuth implementation flow (https://github.com/vikramshanbogar/Spring-Security--SSO-OAuth-JWT-Keycloak/tree/main/KeyCloak-JWT-SpringBoot)
3. SAML flow (https://github.com/vikramshanbogar/Spring-Security--SSO-OAuth-JWT-Keycloak/tree/main/saml-app)

   Notes on Oauth:-

  ### Authorization Code Grant Type
 
 3 step process
 
 1. Request for Code
 2. Using code +(ClientID & client Secret) request for token
 3. Receive Token
 
 Scenario:- All web-applications backed by Server — Recommended
 
 ### Implicit
 

 1. Request for Token Using [ClientID & client Secret]   
 2. Receive Token (Returning access tokens in an HTTP redirect)
 
 Scenario:- SPA or mobile apps where performance is more important(Request for Code is skipped) — Not Recommended — Instead PKCE is used
 
 ### Resource Owner Password Credentials Grant
 
 Scenario:- Typical scenario when user logs in with Username and password (ex: Gmail, Facebook)
 Recommended when user and Resource owner has trust relationship
 
 
 ### Client Credentials Grant
 
 1. Request for Token Using [ClientID & client Secret]
 2. Receive Token
 
 Scenario:- Machine to Machine communication

Note: minor difference between client credentials flow vs Implicit flow, In Implicit flow returning access tokens in an HTTP redirect where as in Client Credentials its directly dependent on [ClientID & client Secret]

### Device code grant 

It enables browser less devices or devices with limited input capabilities to obtain access tokens.

Scenario:- logging into OTT apps on TV using mobile for authentication & Authorization.
