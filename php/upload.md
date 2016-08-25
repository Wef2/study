# Upload
```php
<?php

$uploaddir = 'files/';
$uploadfile = $uploaddir . basename($_FILES['file']['name']);

if (move_uploaded_file($_FILES['file']['tmp_name'], $uploadfile)) {
    echo "Success\n";
} else {
    echo "Error\n";
}

print_r($_FILES);

?>
```
