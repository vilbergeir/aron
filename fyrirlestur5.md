# HLUTI 2: HTML OG PHP

## 📂 Opna vefsíður með PHP (Laragon)

- Setjum öll verkefni í `www` möppuna sem er staðsett í Laragon möppunni undir `C:` drifinu á tölvunni.
- Kveikjum á Laragon og opnum síðuna með því að slá inn:
  ```
  http://localhost/timaverkefni4/main.php
  ```

---

## 🌐 HTML og PHP

- Getum blandað saman HTML og PHP.
- Grunnurinn í HTML verður sá sami og venjulega:
  - `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`

---

## 🖨️ Prenta texta í HTML með PHP

```php
<!DOCTYPE html>
<html>
<body>
<?php echo "<h1>Halló Heimur</h1>"; ?>
</body>
</html>
```

### Prenta breytur í HTML

```php
<html>
<body>
<?php
$message = "Halló Breyta";
echo "<h1>" . $message . "</h1>";
?>
</body>
</html>
```

### Þægilegri leið – HTML aðskilið

```php
<html>
<body>
<?php
$message = "Halló Breyta";
?>
<h1>
<?php echo $message; ?>
</h1>
</body>
</html>
```

---

## 🧠 Skilyrðissetningar: if – elseif – else

### Einföld `if`

```php
<html>
<body>
<h1>
<?php
$age = 43;
if ($age > 40) {
  echo "Þú ert gamall!";
}
?>
</h1>
</body>
</html>
```

### HTML inn í `if`

```php
<html>
<body>
<?php $age = 43; ?>
<?php if ($age > 40): ?>
<h1>Þú ert gamall!</h1>
<?php endif; ?>
</body>
</html>
```

### `if` og `else`

```php
<html>
<body>
<?php $age = 43; ?>
<?php if ($age > 40): ?>
<h1>Þú ert gamall!</h1>
<?php else: ?>
<h2>Þú ert 40 eða yngri!</h2>
<?php endif; ?>
</body>
</html>
```

### `if`, `elseif` og `else`

```php
<html>
<body>
<?php $age = 43; ?>
<?php if ($age > 40): ?>
<h1>Þú ert gamall!</h1>
<?php elseif($age > 30): ?>
<h2>Þú ert á milli 30 og 40</h2>
<?php else: ?>
<h3>Þú ert 30 eða yngri!</h3>
<?php endif; ?>
</body>
</html>
```

---

## 🔗 $_GET – breytur úr slóð (URL)

### Dæmi:

URL:
```
localhost/verkefni/main.php?nafn=John
```

```php
<html>
<body>
<?php $nafn = $_GET['nafn']; ?>
<h1>Nafnið er <?php echo $nafn; ?></h1>
</body>
</html>
```

### Athuga með `isset()` hvort breyta sé til

```php
<html>
<body>
<?php $nafn = isset($_GET['nafn']) ? $_GET['nafn'] : ''; ?>
<h1>Nafnið er <?php echo $nafn; ?></h1>
</body>
</html>
```

### Ná í tölu með `intval()` eða `floatval()`

```php
<html>
<body>
<?php $aldur = isset($_GET['aldur']) ? intval($_GET['aldur']) : 0; ?>
<h1>Aldurinn er <?php echo $aldur; ?></h1>
</body>
</html>
```

---

## 🔁 LYKKJUR – for og foreach

### For lykkja (útskrift í `<p>`)

```php
<html>
<body>
<?php
for($i = 0; $i < 10; $i++) {
  echo "<p>" . $i . "</p>";
}
?>
</body>
</html>
```

### For lykkja með HTML syntax

```php
<html>
<body>
<ul>
<?php for($i = 0; $i < 10; $i++): ?>
  <li><?php echo $i; ?></li>
<?php endfor; ?>
</ul>
</body>
</html>
```

### Foreach lykkja með lista af nöfnum

```php
<html>
<body>
<?php $names = ["Jón", "Sigga", "Ólöf"]; ?>
<ul>
<?php foreach($names as $name): ?>
  <li><?php echo $name; ?></li>
<?php endforeach; ?>
</ul>
</body>
</html>
```
