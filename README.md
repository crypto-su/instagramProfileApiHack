Note: This vulnerability was reported to facebook.

#### instagram ?__a=1 Read Profile

-It also works on a never logged in ip. I sent 10K queries and it didn't give any errors.

#### Php Curl Code

```php
<?php

function r($username){

    $sid = 'sessionid=51190927748%3A7eFw4JGDAh3BYo%3A1;'; // Your Session ID (Google Crome Cookies)
    $headerArr = array("Cookie: $sid");
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://www.instagram.com/'.$username.'/channel/?__a=1');
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headerArr);
    $body = curl_exec($ch);
    curl_close($ch);
    $jsonData = json_decode($body, true);
    return $jsonData;

}

$json = r('elonmusk'); // Username of the user whose information you want to retrieve
print_r ($json);
```
