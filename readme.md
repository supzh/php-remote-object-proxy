# php-remote-object-proxy

easy to use for your project such as \PDO object transfer, or other object you need transfer the in remote.

example:

```php
class test
{
	function func($test){
		return $test . ' works.';
	}
}


$proxy_class = new ObjectProxy(new test);

$a = $proxy_class->func('123');

// get a encode string value can be transfer on http api / database
$encode = Transporter::encode($a);
// ..............
// the other side decode the string then execute the object
$decode = Transporter::decode($encode);
$proxyService = $decode->finishProcedure(); //or new ObjectProxyService($decode);

$result = $proxyService->getResult();

//get a "123 works."
var_dump($result); 
```
