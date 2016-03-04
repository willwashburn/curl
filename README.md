# Curl [![Packagist](https://img.shields.io/packagist/dt/willwashburn/curl.svg)](https://packagist.org/packages/willwashburn/curl) [![Packagist](https://img.shields.io/packagist/v/willwashburn/curl.svg)](https://packagist.org/packages/willwashburn/curl)
1-1 class mapping of the cURL library so it can be mocked / stubbed

Sometimes, you just want to use cURL and not some abstracted class like guzzle. This is a simple wrapper for cURL so you can do that and still write meaningful tests.

# Usage
 ```PHP
class SomeClassThatUsesCurl {


    protected $curl;

    public function __construct(WillWashburn\Curl $curl) {
    
        $this->curl = $curl;
    
    }
    
    public function someMethodThatMakesARequest() {
    
        // Use curl like normal but also be able to test!
        $ch = $this->curl->curl_init($url);
        $this->curl->curl_setopt($ch, CURLOPT_HEADER, true);
    
    }


}
```

# Installation
Use composer

```composer require willwashburn/curl```

Alternatively, add ```"willwashburn/curl": "1.0"``` to your composer.json

