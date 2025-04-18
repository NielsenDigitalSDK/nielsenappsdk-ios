VRI App SDK Release Notes  
For integration help, visit https://engineeringportal.nielsen.com/docs/DCR_&_DTVR

Release 7.2.0.0 (5-18-2020)
- DTVR AQH and IVD requirements for End and pause timeout
- Support for Hybrid app webview measurement
- Support for Hybrid app react native webview measurement
- Support for react native measurement
- Other Bug Fixes and Enhancements.

Release 7.1.0.0 (12-9-2019)
- Removed usage of deprecated class UIWebView 
- Offline viewing measurement enhancements 
- Fixed deadlock on SDK shutdown 
- Revisited precedence logic for sfcode parameter
- Fix for DCR individual ad pings parameters after channel change 
- Using default value for incorrect adModel parameter
- Defaulting isLive parameter value on channel change 
- Other fixes and enhancements.

Release 6.2.0.0 (2-4-2019)
- Removal of Location Module from SDK Code.
- Increased SDK log file size for Debug mode.
- Removed OTT Airplay/mirroring detection that caused crashes in AVAudioSession class.
- DCR performance improvements.
- Fixed the parsing error happening when clientid/vcid provided as empty in metadata.
- Align AppSDK for FW detection with BSDK for DCR measurement.
- Other Bug Fixes/Enhancements.

Release 6.1.0.1 (8-2-2018)
- RTVOD: Nielsen is pursuing the SDK change leveraging TSV service. Clients who wants to use the RTVOD measurement, must get this new SDK. TAM's will need to setup nol_rtvodEnabled flag in the apprepo based on AppID for clients who need RTVOD feature. SDK will continue to send the initial tsv request on receiving the first valid id3 tag, which is the current implementation. When the nol_rtvodEnabled is set to true and if the RTVOD is not detected then in addition to the initial tsv request, SDK will fire a tsv request before every duration ping to detect the RTVOD flag during mid stream. Once the RTVOD flag is detected, no new tsv request will be sent unless there is a FD/PC CID change. In the tsv response sdk will check for the RTVOD flag (03 or 07), denote this as the nol_rtvod parameter in the URL return and the same value will be displayed in cr parameter of the duration ping.
- iOS 12 Changes: AppSDK for support Xcode 10, tvOS 12 and iOS 12. The iOS 12 change includes transitioning from  UIWebView to WKWebView since the UIWebView class was officially deprecated. No changes for tvOS 12.

Release 6.0.0.4 (5-24-2018)
WARNING: Switching between 5th and 6th major versions will cause compile time error if you use New Enhanced API.

- If the SDK build target is set to AGF then SDK will send the hello ping to “eu” and “eu-uat” for debug builds. No changes to the non AGF build the default sfcode will continue to be sdk and cert for debug build.
- The C1 parameter (NUID) will now be sent as encrypted DeviceID.
- New SessionID changes. The sessionID will contain 29 length random characters appended by timestamp.
- Support for multiple SDK instance without any limit.
- New log feature for CAT tool to retrieve the API level information from client apps. This ping will contain the eventType, parameters, SDK version, appid etc.

Release 5.1.1.29 (7-21-2017)
- Genre parameter will be a part of DCR pings and the value will be reflected as part of c44 parameter.
- Merged adModel and adLoadType flags
- Fix for stop event data carried to next session’s duration ping
