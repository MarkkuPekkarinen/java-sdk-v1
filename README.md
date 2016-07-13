GSMA MobileConnect Java SDK
==============================================================================================================

- Example of GSMA MobileConnect SDK Integration in Java application
- This demo provides a complete code example for completing the authorization flow of MobileConnect
- Demo code is only for example purposes

Minimum Requirements
-----------------
MobileConnect supports Java 1.5, and is dependent upon Jackson Databind 2.6.3 and Apache HTTP Client 4.5.1.

Getting Started
-----------------
You must have first registered an account on the [MobileConnect Developer Site](https://developer.mobileconnect.io) and created an application to get your sandbox credentials.

Using the credentials from your account page replace the credentials in com.gsma.mobileconnect.demo.App.

Build and run the application.

Using The SDK
---------------
Install the SDK to your local [Maven](https://maven.apache.org/) repository.

```posh
mvn clean install
```

Configure your MobileConnect options within App.java

```java
MobileConnectConfig mobileConnectConfig = new MobileConnectConfig();
mobileConnectConfig.setClientId("944b6cfd-8386-4817-8567-7e444e188e48");
mobileConnectConfig.setClientSecret("5440107a-1f4a-4cf6-8226-94443de6692f");
mobileConnectConfig.setApplicationURL("http://localhost:8080/mobile_connect");
mobileConnectConfig.setDiscoveryURL("http://discovery.sandbox2.mobileconnect.io/v2/discovery");
```

Please reference the demo application for an example of how to use the SDK.

## Demo Application

Run the MobileConnect demo.

```posh
mvn spring-boot:run
```

Then navigate to http://localhost:8080 in your browser.

## Support

If you encounter any issues which are not resolved by consulting the resources below then [send us a message](https://developer.mobileconnect.io/content/contact-us)

## Resources

- [MobileConnect Discovery API Information](https://developer.mobileconnect.io/content/discovery-api-0)
- [MobileConnect Authentication API Information](https://developer.mobileconnect.io/content/mobile-connect-api)
