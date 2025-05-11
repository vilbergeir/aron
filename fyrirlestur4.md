# HLUTI 1: KYNNING Á PHP  
## Hluti 4 – Vinna með fylki

---

## 🔁 Fylki

- Við höfum áður skoðað:
  - Aðferðir til að fara í gegnum fylki
  - Ná í gildi úr fylki
  - Lyklafylki (associative arrays)

- Nú skoðum við:
  - Hvernig við breytum, bætum við og vinnum með fylki

---

## ✏️ Uppfæra gildi í fylki

```php
<?php
$numbers = [2, 3, 4, 5, 6];
$numbers[2] = 8; // $numbers = [2, 3, 8, 5, 6];
?>
```

---

## ➕ Bæta við hlutum í fylki

```php
<?php
$numbers = [2, 3, 4, 5, 6];
array_push($numbers, 10); // $numbers = [2, 3, 4, 5, 6, 10];
?>
```

---

## ➕ Bæta við í lyklafylki

```php
<?php
$person = ["name" => "Jón", "age" => 32];
$person["town"] = "Reykjanesbær";
// $person = ["name" => "Jón", "age" => 32, "town" => "Reykjanesbær"];
?>
```

---

## ❌ Eyða úr fylki

```php
<?php
$numbers = [1, 2, 3, 4, 5];
unset($numbers[2]); // $numbers = [1, 2, 4, 5];
?>
```

---

## 🔑 Ná í alla lykla úr lyklafylki

```php
<?php
$person = [
  "name" => "Jón",
  "age" => 32,
  "town" => "Reykjavík"
];
$keys = array_keys($person); // ["name", "age", "town"]
?>
```
