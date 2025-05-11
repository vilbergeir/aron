# HLUTI 2: HTML OG PHP  
## Glærur 2 – Fylki af lyklafylkjum

---

## 🧱 Fylki af lyklafylkjum

- Getum verið með fylki sem inniheldur lyklafylki (associative arrays).

```php
<?php
$movies = [
  ["name" => "Deadpool", "rating" => 8],
  ["name" => "Avatar", "rating" => 7]
];
?>
```

---

## 🖨️ Prenta upplýsingar úr lyklafylkjum

```php
<?php foreach($movies as $movie): ?>
  <h1><?php echo $movie['name']; ?></h1>
  <p><?php echo $movie['rating']; ?></p>
<?php endforeach; ?>
```

---

## ✅ Með `if` skilyrðum

```php
<?php foreach($movies as $movie): ?>
  <h1><?php echo $movie['name']; ?></h1>
  <?php if ($movie['rating'] > 7): ?>
    <p><?php echo $movie['rating']; ?></p>
  <?php endif; ?>
<?php endforeach; ?>
```
