# sdk-ebay-rest-media

The Media API allows sellers to create, upload, and fetch videos.


## Installation & Usage

### Requirements

PHP 7.3 and later.
Should also work with PHP 8.0 but has not been tested.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/macropage/sdk-ebay-rest-media.git"
    }
  ],
  "require": {
    "macropage/sdk-ebay-rest-media": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/sdk-ebay-rest-media/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure OAuth2 access token for authorization: Authorization Code
$config = macropage\SDKs\ebay\rest\media\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new macropage\SDKs\ebay\rest\media\Api\VideoApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \macropage\SDKs\ebay\rest\media\Model\CreateVideoRequest(); // \macropage\SDKs\ebay\rest\media\Model\CreateVideoRequest

try {
    $apiInstance->createVideo($body);
} catch (Exception $e) {
    echo 'Exception when calling VideoApi->createVideo: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://apim.ebay.com/commerce/media/v1_beta*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*VideoApi* | [**createVideo**](docs/Api/VideoApi.md#createvideo) | **POST** /video | 
*VideoApi* | [**getVideo**](docs/Api/VideoApi.md#getvideo) | **GET** /video/{video_id} | 
*VideoApi* | [**uploadVideo**](docs/Api/VideoApi.md#uploadvideo) | **POST** /video/{video_id}/upload | 

## Models

- [CreateVideoRequest](docs/Model/CreateVideoRequest.md)
- [Image](docs/Model/Image.md)
- [Moderation](docs/Model/Moderation.md)
- [Play](docs/Model/Play.md)
- [Video](docs/Model/Video.md)

## Authorization

### Authorization Code

- **Type**: `OAuth`
- **Flow**: `accessCode`
- **Authorization URL**: `https://auth.ebay.com/oauth2/authorize`
- **Scopes**: 
    - **https://api.ebay.com/oauth/api_scope/sell.inventory**: View and manage your inventory and offers

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `v1_beta.1.0`
    - Package version: `2.3.2`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
