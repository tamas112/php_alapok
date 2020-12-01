# Hello friend. <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px"> 
![](https://img.shields.io/badge/Language-C-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=2bbc8a) ![](https://img.shields.io/badge/Practice-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=dbde31) ![](https://img.shields.io/badge/Console_Application-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=black) 

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
