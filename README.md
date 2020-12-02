# Hello friend. <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px"> 
![](https://img.shields.io/badge/Language-PHP-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=7e00b0) ![](https://img.shields.io/badge/Knowledge_base-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=b55c5c) 

//PHP snippets ⭐

### 1. MySQL Snippets
This snippet will connect to your MySQL database:
```php
$mysqli = mysqli_connect('localhost', 'DATABASE_USER', 'DATABASE_PASS', 'DATABASE_NAME');
```
Check for connection errors:
```php
if (mysqli_connect_errno()) {
	die('Failed to connect to MySQL: ' . mysqli_connect_error());
}
```
Select database table and display all the results:
```php
$result = $mysqli->query('SELECT * FROM students');
while ($row = $result->fetch_assoc()) {
	echo $row['name'] . '<br>';
}
```
Checking the number of rows:
```php
$result->num_rows;
```
Insert a new record:
```php
$mysqli->query('INSERT INTO students (name) VALUES ("David")');
```
Checking the number of affected rows:
```php
$mysqli->affected_rows;
```
Escape special characters in a string, this should be used if you do not prepare your statements:
```php
$mysqli->real_escape_string($user_input_text);
```
Prepare statement, prevents SQL injection:
```php
$name = 'David';
$limit = 1;
$stmt = $mysqli->prepare('SELECT * FROM students WHERE name = ? LIMIT ?');
$stmt->bind_param('si', $name, $limit);
$stmt->execute();
// etc...
$result = $stmt->get_result();
```
Close query and close database connection:
```php
$stmt->close();
$mysqli->close();
```

### 2. Escape HTML Entities
This snippet will escape HTML entities and quotes:
```php
htmlentities($text, ENT_QUOTES, "UTF-8");
```
Decoding HTML entities:
```php
html_entity_decode($text);
```


### 3. Replace Text in String
This snippet will replace text in a string:
```php
str_replace('Apple', 'Orange', 'My favourite fruit is an Apple.');
```
And to replace multiple words in a string:
```php
str_replace(array('fruit', 'Apple'), array('Vegetable', 'Carrot'), 'My favourite fruit is an Apple.');
```

### 4. Check if a String Contains a Specific Word
This snippet will check if a string contains a specific word:
```php
if (strpos('My name is David.', 'David') !== false) {
	// String contains David
}
```

### 5. Array Snippets
Inserting new items into an array:
```php
$names = array();
array_push($names, 'David', 'John');
```
Remove item from an array:
```php
unset($names['David']);
// or...
unset($names[0]);
```
Reindex the values after you have removed an item:
```php
$names = array_values($names);
```
Reverse an array:
```php
$reversed = array_reverse($names);
```
Merge two or more arrays:
```php
$merged = array_merge($arr1, $arr2);
```
Return only the array keys:
```php
$keys = array_keys(array('name' => 'David', 'age' => 28));
```
Sort an array:
```php
sort($names);
```
Sort an array in reverse order:
```php
rsort($names);
```
Check if item exists in an array:
```php
if (in_array('David', $names)) {
	// item exists
}
```
Check if key exists in an array:
```php
if (array_key_exists('name', array('name' => 'David', 'age' => 28))) {
	// key exists
}
```
Count the number of items in an array:
```php
count($names);
```
Convert comma-separated list to array:
```php
$array = explode(',', 'david,john,warren,tracy');
```

### 6. GET and POST Requests
Get an value from the URL parameters:
```php
// index.php?name=david
echo $_GET['name'];
```
Check if request variable exists:
```php
if (isset($_GET['name'])) {
	// exists
}
```
Send form data to PHP script, HTML file:
```php
<form action="login.php" method="post">
	Username: <input type="text" name="username"><br>
	Password: <input type="password" name="password"><br>
	<input type="submit">
</form>
```
login.php:
```php
$user = $_POST['username'];
$pass = $_POST['password'];
echo 'Your username is '  . $user . ' and your password is ' . $pass . '.';
```

### 7. Create a Password Hash
This snippet will create a password hash:
```php
$hash = password_hash('your_password', PASSWORD_DEFAULT);
```
Verify your hashed passwords:
```php
if (password_verify('your_password', $hash)) {
	// hash is valid
}
```


### 8. Sessions
This snippet will create a new session, sessions act as cookies but are stored on the server instead of the clients computer.
```php
session_start();
$_SESSION['name'] = 'David';
```
Free all the session variables:
```php
session_unset();
```
Destroy all the session variables:
```php
session_destroy();
```

### 9. Redirect URL
This snippet will redirect to a new page:
```php
header("Location: http://example.com/newpage.php");
```

### 10. Get the Clients IP Address
This snippet will get the IP address of the client:
```php
if (!empty($_SERVER['HTTP_CLIENT_IP'])) {
    $ip = $_SERVER['HTTP_CLIENT_IP'];
} elseif (!empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
    $ip = $_SERVER['HTTP_X_FORWARDED_FOR'];
} else {
    $ip = $_SERVER['REMOTE_ADDR'];
}
```

### 11. Get the Contents of a URL File
This snippet will get the contents of a file using cURL:
```php
$url = 'http://example.com/file.json';
$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_HEADER, false);
curl_setopt($curl, CURLOPT_FOLLOWLOCATION, true);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, false);
$result = curl_exec($curl);
curl_close($curl);
```
Using PHP file_get_contents:
```php
$result = file_get_contents('file.json');
```

### 12. Determine the Date
This snippet will get the current date in string format:
```php
$date = date('Y-m-d H:i:s');
echo $date;
```
Get the date from a timestamp:
```php
$date = date('Y-m-d H:i:s', $timestamp);
echo $date;
```

### 13. JSON
This snippet will get an JSON file and decode it:
```php
$string = file_get_contents('file.json');
$json = json_decode($string, true);
// $json['name'] etc...
```
Encode PHP array to JSON:
```php
$array = array('name' => 'David', 'age' => 27);
$string = json_encode($array);
echo $string; // { "name" : "David", "age" : 27 }
```

### 14. Memcached
Connect to memcached server:
```php
$memcached = new Memcached();
$memcached->addServer('127.0.0.1', 11211);
```
Set item:
```php
$memcached->set('name', 'David');
```
Get item:
```php
$memcached->get('name');
```

### 15. Send Email
This snippet will send an email:
```php
$to      = 'nobody@example.com';
$subject = 'the subject';
$message = 'hello';
$headers = 'From: webmaster@example.com' . "\r\n" . 'Reply-To: webmaster@example.com' . "\r\n" . 'X-Mailer: PHP/' . phpversion();
mail($to, $subject, $message, $headers);
```

### 16. Display the Scripts Execution Time
This snippet will display the scripts execution time:
```php
$time_start = microtime(true); 
// Your scripts here...
echo 'Total execution time in seconds: ' . (microtime(true) - $time_start);
```

### 17. Get the Full URL
This snippet will get the full URL of your website (replace HTTP with HTTPS if your site is SSL):
```php
$url = 'http://' . $_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI'];
```

### 18. Format Numbers
This snippet will format your number with a comma:
```php
$num = number_format(1000); 
echo $num; // 1,000
```
Format number with decimals:
```php
$num = number_format(1000.12, 2); 
echo $num; // 1,000.12
```

### 19. Unzip a File
This snippet will unzip a zipped file on your server:
```php
$zip = new ZipArchive;
$file = $zip->open('file.zip');
if ($file) {
	$zip->extractTo('/extract_path/');
	$zip->close();
	echo 'Archive extracted!';
}
```

### 20. Detect Mobile Device
This snippet will detect if the client is using a mobile device:
```php
if (preg_match("/(android|avantgo|blackberry|bolt|boost|cricket|docomo|fone|hiptop|mini|mobi|palm|phone|pie|tablet|up\.browser|up\.link|webos|wos)/i", $_SERVER["HTTP_USER_AGENT"])) {
	// Is mobile...
}
```

### 21. Check if File Exists
This snippet will check if a file exists:
```php
if (file_exists('example.png')) {
	// File exists
}
```


source: https://codeshack.io/21-useful-php-snippets/
