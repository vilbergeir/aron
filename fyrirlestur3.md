# HLUTI 1: KYNNING Á PHP  
## Hluti 3 – Semíkomma, föll, lyklafylki og strengir

---

## 🔚 Semíkomma

- Allar skipanir í PHP enda á **semíkommu (;)**

```php
<?php
$name = "Jón Jónsson";
echo $name;
?>
```

- Ekki þarf að nota semíkommu á eftir slaufusvigum (`{}`) í `if`, `elseif`, `else` og föllum:

```php
<?php
$age = 30;
if ($age > 20) {
  echo "Eldri en 20 ára";
}
?>
```

---

## 🧩 Föll (functions)

- Við búum til föll í PHP með `function`:

```php
<?php
function printHelloWorld() {
  echo "Hello World";
}
printHelloWorld();
?>
```

- Föll geta **skilað gildi** með `return`:

```php
<?php
function getHelloWorldText() {
  return "Halló Heimur";
}
echo getHelloWorldText(); // Prentar "Halló Heimur"
?>
```

- Föll geta tekið við **færibreytum**:

```php
<?php
function mismunur($x, $y) {
  return abs($x - $y);
}
echo mismunur(3, 10); // Prentar 7
?>
```

- Færibreytur geta haft **sjálfgefið gildi**:

```php
<?php
function printMsg($msg = "Hello World") {
  echo $msg;
}
printMsg(); // "Hello World"
printMsg("FooBar"); // "FooBar"
?>
```

---

## 🗂️ Lyklafylki (associative arrays)

- Í stað staðsetninga 0, 1, 2... notum við nöfn sem lykla:

```php
<?php
$person = ["name" => "John", "age" => 23];
?>
```

- Ná í gögn úr lyklafylki:

```php
<?php
$person = ["name" => "John", "age" => 23];
echo $person["name"]; // "John"
?>
```

- Nota `foreach` til að fara í gegnum:

```php
<?php
$person = ["name" => "John", "age" => 23];
foreach($person as $key => $value) {
  echo $key;
  echo $value;
}
?>
```

---

## 🔤 Strengir

- Ýmis gagnleg föll til að vinna með strengi.

### Finna lengd strengs

```php
<?php
$message = "Halló Allir";
echo strlen($message);
?>
```

### Taka hluta úr streng

```php
<?php
$message = "Halló Allir";
echo substr($message, 6);      // "Allir"
echo substr($message, 4, 2);   // "Ló"
?>
```

### Breyta texta í streng með `str_replace()`

```php
<?php
$message = "Halló Allir";
echo str_replace("Allir", "Heimur", $message); // "Halló Heimur"
echo str_replace("Halló", "Bæ", $message);     // "Bæ Allir"
?>
```

---

## ➕ Fleiri gagnleg föll

- **Reikningsföll**
- **Strengjaföll**
- **Fylkjaföll**
