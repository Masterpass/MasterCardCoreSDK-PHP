# Read Me

PHP Core SDK for use with Masterpass Merchant Checkout Service SDK on MasterCard Developer Zone (https://developer.mastercard.com) 

Pre-Requisites for using PHP MasterCard Core SDK:

 *  PHP 5.5 or higher
 *  Download MasterCardCoreSDK-PHP phar file
 
 ##### Note: Refer to mastercard developer zone for documentation on SDKs for implementation reference and avoid potential break in your existing code if you upgrade with higher version.
 
 
##### Documentation for SDK Integration: 

For Masterpass V6 : 

For configuration and pre-requisites: https://developer.mastercard.com/documentation/masterpass-merchant-integration-v6
For standard/express checkout integration: https://developer.mastercard.com/documentation/masterpass-merchant-integration-v6#tutorials

For Masterpass V7:

For configuration and pre-requisites https://developer.mastercard.com/documentation/masterpass-merchant-integration-v7
For standard checkout integration: https://developer.mastercard.com/documentation/masterpass-merchant-integration-v7#standard-checkout 
For express checkout integration: https://developer.mastercard.com/documentation/masterpass-merchant-integration-v7#express-checkout 
 
This phar can be downloaded from github directly or by using composer dependency.
 
 If you do not have composer installed you can download it from https://getcomposer.org/
 
 To download this phar as composer dependency, put a file named composer.json at the root of your project, containing as your project dependencies:
 
 MasterCardCoreSDK v6 :
 ```
 {
    "require": {
      "masterpass/mpasscoresdk":"1.3.0"
    }
 }
```
 MasterCardCoreSDK v7 :
 ```
 {
    "require": {
      "masterpass/mpasscoresdk":"2.2.0"
    }
 }
```

In order to import this package in your application, you need to use following composer command after installing composer locally:

> composer update

## Usage

Set configurations for private key and consumer key to call API: 

```

MasterCardApiConfig::$consumerKey = "YOUR_CONSUMER_KEY";
MasterCardApiConfig::$privateKey = "YOUR_PRIVATE_KEY";
MasterCardApiConfig::setSandBox(true); // For sandbox environment. By default SANDBOX environment is set as true, Set sandbox to false to use Production environment

```

Customize default SSL settings for the SDK through Configuration class using following code: 
[You may get SSL Exception if there is no already configured ssl certificate file exists locally or in php.ini]
Note: SSL Verification is set to True by default. Do NOT set it to false in production code, otherwise you would face multiple types of cryptographic attacks. 

```

$conf = new Configuration();
$conf->setSSLVerification("C:\\Users\\Documents\\cert.pem");
Configuration::setDefaultConfiguration($conf);

```

Example : Api Call

```

$RequestTokenResponse = RequestTokenApi::create(<URL>);

```

You can get more information about integrating MasterCard Merchant Checkout SDK from MasterCard Developer Zone - 
##### Merchant Integration section. 