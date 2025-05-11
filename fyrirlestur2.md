# HLUTI 1: KYNNING Á PHP  
## Hluti 2 – PHP Tög, breytur, skilyrði, lykkjur og fylki

---

## 🏷️ PHP tög

- Í PHP skrám þarf að setja PHP tög utan um allan PHP kóða.
- PHP tögin eru `<?php` og `?>`.

```php
<?php echo "Halló Heimur"; ?>
```

```php
<!DOCTYPE html>
<html>
<body>
<h1>My first PHP page</h1>
<?php
echo "Hello World!";
?>
</body>
</html>
```

---

## 💾 Breytur

- Breytur í PHP byrja á `$` merkinu.

```php
<?php
$name = "Jón Jónsson";
$age = 45;
?>
```

- Hægt er að reikna með tölum:

```php
<?php
$x = 5;
$y = 4;
echo $x + $y;
?>
```

---

## 🖨️ Echo – prenta út

- `echo` er skipun til að prenta út (eins og `print` í Python).

```php
<?php
echo "Hello World";
?>
```

- Prenta út breytur:

```php
<?php
$name = "John";
echo $name;
?>
```

- Prenta HTML tög:

```php
<?php
echo "<h2>Hello Universe!</h2>";
echo "Hello world!<br>";
?>
```

- Tengja saman texta með punkt:

```php
<?php
$txt1 = "PHP";
$txt2 = "Heimur";
echo "<h2>" . $txt1 . "</h2>";
echo "Halló " . $txt2 . "<br>";
?>
```

---

## 🔀 IF – ELSE – ELSEIF

- Skilyrðissetningar til að keyra kóða eftir aðstæðum:

```php
<?php
$age = 32;
if ($age > 30) {
  echo "Aldurinn er hærri en 30";
}
?>
```

- Með else:

```php
<?php
$age = 32;
if ($age > 30) {
  echo "Aldurinn er hærri en 30";
} else {
  echo "Aldurinn er 30 ára eða minni";
}
?>
```

- Með else if:

```php
<?php
$age = 32;
if ($age > 30) {
  echo "Aldurinn er hærri en 30";
}
else if ($age > 20) {
  echo "Aldurinn er á milli 21-30";
}
else {
  echo "Hver er aldurinn?";
}
?>
```

---

## 🔁 Lykkjur

- `for` lykkja:

```php
<?php
for ($i = 0; $i < 10; $i++) {
  echo $i;
}
?>
```

- `while` lykkja:

```php
<?php
$i = 0;
while ($i < 10) {
  echo $i;
  $i++;
}
?>
```

---

## 📚 Fylki

- Búa til fylki:

```php
<?php
$cars = ["Volvo", "Benz", "Honda"];
?>
```

- Finna stærð fylkis:

```php
<?php
$cars = ["Volvo", "Benz", "Honda"];
echo count($cars); // Prentar út 3
?>
```

- Ná í gildi með index:

```php
<?php
$cars = ["Volvo", "Benz", "Honda"];
echo $cars[0]; // Prentast út "Volvo"
echo $cars[2]; // Prentast út "Honda"
?>
```

- Prenta allt fylkið með `for` lykkju:

```php
<?php
$cars = ["Volvo", "Benz", "Honda"];
for ($i = 0; $i < count($cars); $i++) {
  echo "<p>" . $cars[$i] . "</p>";
}
?>
```

- Prenta allt fylkið með `foreach` lykkju:

```php
<?php
$cars = ["Volvo", "Benz", "Honda"];
foreach($cars as $car) {
  echo $car;
}
?>
```
