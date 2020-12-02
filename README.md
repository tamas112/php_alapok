# Hello friend. <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px"> 
![](https://img.shields.io/badge/Language-PHP-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=7e00b0) ![](https://img.shields.io/badge/Knowledge_base-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=b55c5c) 

//PHP és MYSQL alapok ⭐


Adatbázis kapcsolat létesítés: 
```php
$mysqli = mysqli_connect('localhost', 'DATABASE_USER', 'DATABASE_PASS', 'DATABASE_NAME');
```


Adatbázis kapcsolat ellenőrzése:
```php
if (mysqli_connect_errno()) { 
	die('Sikertelen csatlakozás a MYSQL adatbázishoz: ' . mysqli_connect_error());
}
```
