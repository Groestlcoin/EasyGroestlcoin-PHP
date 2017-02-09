EasyGroestlcoin-PHP
===============

A simple class for making calls to Groestlcoin's API using PHP.

Getting Started
---------------
1. Include easygroestlcoin.php into your PHP script:

    ```php
    require_once('easygroestlcoin.php');
    ```
2. Initialize Groestlcoin connection/object:

    ```php
    $groestlcoin = new Groestlcoin('username','password');
    ```

    Optionally, you can specify a host, port. Default is HTTP on localhost port 1441.

    ```php
    $groestlcoin = new Groestlcoin('username','password','localhost','1441');
    ```

    If you wish to make an SSL connection you can set an optional CA certificate or leave blank
    ```php
    $groestlcoin->setSSL('/full/path/to/mycertificate.cert');
    ````

3. Make calls to groestlcoind as methods for your object. Examples:

    ```php
    $groestlcoin->getinfo();
    
    $groestlcoin->getrawtransaction('cf72b5842b3528fd7f3065ba9e93c50a62e84f42b3b7b7a351d910b5e353b662',1);
    
    $groestlcoin->getblock('00000ac5927c594d49cc0bdb81759d0da8297eb614683d3acb62f0703b639023');
    ```

Additional Info
---------------
* When a call fails for any reason, it will return false and put the error message in `$groestlcoin->error`

* The HTTP status code can be found in $groestlcoin->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in `$groestlcoin->response` while the raw JSON is stored in `$groestlcoin->raw_response`
