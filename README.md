NativeScript iZettle plugin
===========================
Accept payments directly in your NativeScript app with [iZettle](https://www.izettle.com/).

<img src="https://raw.githubusercontent.com/EddyVerbruggen/nativescript-izettle/master/media/izettle-card-reader.png" width="644px" height="400px">

## Supported platforms
* iOS, using the [iZettleSDK CocoaPod](https://cocoapods.org/?q=iZettleSDK)
* (iZettle doesn't have an SDK for Android yet)

## Features
* Fully integrated payment flow (no app-to-app switching, no installed iZettle app required).
* Extremely simple API - just pass in an amount and you're done.
* After a payment completes you'll get info on the payment type and status so your app can respond appropriately.

## Payment API
You can use the plugin with JavaScript or TypeScript. In case of the latter, the relevant code is:

```typescript
  new IZettle().pay({
    apiKey: "your-iZettle-API-key",
    amount: 100, // 100 USD/EUR/.., depends on the configuration of your iZettle account
    reference: "your optional app payment reference"
  }).then((result: IZettlePaymentResult) => {
    // Payment succeeded, the result object contains:
    // 'entryMode', 'referenceNumber', 'obfuscatedPan', 'cardBrand', 'authorizationCode', 'applicationName'.

  }, (error: IZettleError) => {
    // No need to show the error to the user as that has already been done by the iZettle UI,
    // but the error object contains a 'message' and 'code' anyway.
  });

```

## Want to use this plugin?
For various reasons the plugin code is not out there in the wild, so if you want to use this plugin,
please contact me at eddyverbruggen at gmail dot com.