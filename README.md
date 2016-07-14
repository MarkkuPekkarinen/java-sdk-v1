GSMA MobileConnect Java SDK
==============================================================================================================

Mobile Connect is a mobile identity service based on the OpenID Connect & OAuth2 where end users can authenticate themselves using their mobile phone via Mobile Connect. This allows them access to websites and applications without the need to remember passwords and usernames. It’s safe, secure and no personal information is shared without their permission.

## Minimum Requirements

MobileConnect supports Java 1.5, and is dependent upon Jackson Databind 2.6.3 and Apache HTTP Client 4.5.1.

## Getting Started

You must have first registered an account on the [MobileConnect Developer Site](https://developer.mobileconnect.io) and created an application to get your sandbox credentials.

## Using The SDK

Build the SDK using [Maven](https://maven.apache.org/) repository.

```posh
cd mobile-connect-sdk
mvn clean install
```

Import the generated mobile-connect-sdk-1.0.0-jar into your java project.

You will need to specify your credentials via an instance of MobileConnectConfig.

```java
MobileConnectConfig config = new MobileConnectConfig();
mobileConnectConfig.setClientId("944b6cfd-8386-4817-8567-7e444e188e48");
mobileConnectConfig.setClientSecret("5440107a-1f4a-4cf6-8226-94443de6692f");
mobileConnectConfig.setApplicationURL("http://localhost:8080/mobile_connect");
mobileConnectConfig.setDiscoveryURL("http://discovery.sandbox2.mobileconnect.io/v2/discovery");
```

You must create instances of both IDiscovery and IOIDC.  Factory can help with this.

```java
IDiscovery discovery = Factory.getDiscovery(Factory.getDefaultDiscoveryCache());
IOIDC oidc = Factory.getOIDC();
```

The main entry point to start the authorisation process is via the MobileConnectInterface class.

```java
MobileConnectStatus status;

status = MobileConnectInterface.callMobileConnectForStartDiscovery(discovery, config, servletRequest, servletResponse)
...
status = MobileConnectInterface.callMobileConnectOnDiscoveryRedirect(discovery, config, servletRequest, servletResponse);
...
status = MobileConnectInterface.callMobileConnectForStartAuthorization(oidc, config, servletRequest);
...
status = MobileConnectInterface.callMobileConnectOnAuthorizationRedirect(oidc, config, servletRequest);
```

Please reference the [demo application](mobile-connect-demo/) for a complete example of how to use the SDK.

## Support

If you encounter any issues which are not resolved by consulting the resources below then [send us a message](https://developer.mobileconnect.io/content/contact-us)

## Resources

- [MobileConnect Discovery API Information](https://developer.mobileconnect.io/content/discovery-api-0)
- [MobileConnect Authentication API Information](https://developer.mobileconnect.io/content/mobile-connect-api)
