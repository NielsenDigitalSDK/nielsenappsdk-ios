Nielsen App SDK Release Notes

Release 6.2.0.0 (2-4-2019)
- Location measurement has been removed from the SDK code.
- Location frameworks were there previously but disabled, now it’s fully removed to avoid confusion from noticing it being included at all. Code was there because SDK used to collect. Then the function was disabled. Even having it there, clients used to be like "why are you having that framework there?" It raised privacy/security concerns and suspicion.
- Increased SDK log file size from 2mb limit to 50mb for Debug mode. Logs will not rollover so quickly so that longer debug sessions can be analyzed.
- Removed OTT Airplay/mirroring detection that caused crashes in AVAudioSession class.
- DCR performance improvements.
- Fixed the parsing error happening when clientid/vcid provided as empty in metadata. In case where clientid/vcid is not supplied, SDK will take default from config instead of using the blank value.
- Implemented buildversion naming convention. Help monitor SDK flavor (artifactory/Adobe Launch/standalone/etc) and market (AGF/Global).
- Align AppSDK for FW detection with BSDK where for DCR use a variable nol_cmsIntrvlGp (value is 2) rather than nol_id3IntrvlGp(15). Detect forward event with >2 seconds of scrub for DCR instead of 15 seconds as currently. This may result in more FW events in EVdata as well as less duration.
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
