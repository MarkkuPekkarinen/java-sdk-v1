GSMA MobileConnect Java SDK Demo Application
==============================================================================================================

- Example of GSMA MobileConnect SDK Integration in Java application
- This demo provides a complete code example for completing the authorization flow of MobileConnect
- Demo code is only for example purposes

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
mobileConnectConfig.setClientId("944b6cfd-8386-4817-8567-7e444e188e48");
mobileConnectConfig.setClientSecret("5440107a-1f4a-4cf6-8226-94443de6692f");
mobileConnectConfig.setApplicationURL("http://localhost:8080/mobile_connect");
mobileConnectConfig.setDiscoveryURL("http://discovery.sandbox2.mobileconnect.io/v2/discovery");
```

Run the MobileConnect demo.

```posh
mvn spring-boot:run
```

Then navigate to http://localhost:8080 in your browser.
