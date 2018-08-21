Nielsen AGF No Ad App SDK

6.0.0.4
- If the SDK build target is set to AGF then SDK will send the hello ping to “eu” and “eu-uat” for debug builds. No changes to the non AGF build the default sfcode will continue to be sdk and cert for debug build.
- The C1 parameter (NUID) will now be sent as encrypted DeviceID.
- New SessionID changes. The sessionID will contain 29 length random characters appended by timestamp.
- Support for multiple SDK instance without any limit.
- New log feature for CAT tool to retrieve the API level information from client apps. This ping will contain the eventType, parameters, SDK version, appid etc.
