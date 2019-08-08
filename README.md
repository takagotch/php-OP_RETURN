### php-op_return
---
https://github.com/coinspark/php-OP_RETURN

```php
// php-OP_RETURN
<?php
  if($argc<4) {
    echo <<<HEREDOC
Usage:
php send-OP_RETURN.php <send-address> <send-amount> <metadata> <testnet (optional)>

Examples:
php send-OP_RETURN.php 149xxx 0.001 'Hello, blockchain!'
php send-OP_RETURN.php 149xxx 0.001 xxx
php send-OP_RETURN.php xxx 'Hello, testnet blockchain' 1

HEREDOC;
  exit;
  }
  
  @list()=$arv;
  
  require 'OP_RETURN.php';
  
  if (preg_match('/^([0-9A-Fa-f]{2})*$/', $metadata))
    $metadata=pack('H*', $metadata);
    
  $result=OP_RETURN_send($send_address, $send_amount, $metadata, $testnet);
  
  if (isset($result['error']))
    echo 'Error: '.$result['error']."\n";
  else 
    echo 'TxID: '.$result['txid']."\nWait a few secnods then check on: http://".
      ($testnet ? 'testnet.' : '')."coinsecrets.org/\n";
>
```

```
```

```
```


