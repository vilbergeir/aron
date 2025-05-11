# HLUTI 2: HTML OG PHP  
## Glærur 2 – Gagnagrunnar

---

## 🔌 Tenging við gagnagrunn

- PHP og gagnagrunnar eru tveir mismunandi hlutir.
- Áður en við byrjum að nota gagnagrunna í PHP þurfum við að setja upp töflur og gögn í gagnagrunninn (sjá skrá á Moodle).
- Til að nota gagnagrunna í PHP þurfum við fyrst að tengjast gagnagrunni úr PHP kóða.
- Við notum PDO til að tengjast MySQL:

```php
<?php
$database = 'vefforritun';
$user = 'root';
$password = '';
$dsn = "mysql:host=127.0.0.1;dbname=" . $database . ";charset=utf8";

try {
  $pdo = new PDO($dsn, $user, $password);
} catch (\PDOException $e) {
  die($e->getMessage());
}
?>
```

- Fyrri hlutinn: skilgreina tengistreng og notanda.
- Seinni hlutinn: reyna að tengjast gagnagrunni og prenta villuskilaboð ef það mistekst.

---

## 🧾 SQL skipanir

- Þegar tengingu er náð, getum við gert SQL skipanir með PHP til að:
  - Sækja gögn (SELECT)
  - Uppfæra, bæta við eða eyða gögnum

---

## 🔍 SELECT skipun

```php
<?php
$query = $pdo->query("SELECT * FROM nemandi");
$nemendur = $query->fetchAll();
?>
```

### Dæmi um gögn sem við gætum fengið:

```php
<?php
$nemendur = [
  ['id' => 1, 'nafn' => 'Sigurður', 'faeddur' => 2002],
  ['id' => 2, 'nafn' => 'Anna',     'faeddur' => 1989],
  ['id' => 3, 'nafn' => 'Pétur',    'faeddur' => 1995],
  ['id' => 4, 'nafn' => 'Tinna',    'faeddur' => 2001],
];
?>
```

### Birta allar raðir

```php
<?php foreach($nemendur as $nemandi): ?>
  <p><?php echo $nemandi["nafn"]; ?></p>
<?php endforeach; ?>
```

### Birta mismunandi HTML eftir fæðingarári

```php
<?php foreach($nemendur as $nemandi): ?>
  <?php if($nemandi["faeddur"] >= 2000): ?>
    <h3 class="blue"><?php echo $nemandi["nafn"]; ?></h3>
  <?php else: ?>
    <h2 class="red"><?php echo $nemandi["nafn"]; ?></h2>
  <?php endif; ?>
<?php endforeach; ?>
```

---

## 🎯 Velja ákveðna dálka

```php
<?php
$query = $pdo->query("SELECT nafn FROM nemandi");
$nemendur = $query->fetchAll();
?>
```

---

## 📌 WHERE – velja aðeins ákveðnar raðir

```php
<?php
$query = $pdo->query("SELECT * FROM nemandi WHERE faeddur < 2000");
$nemendur = $query->fetchAll();
?>
```

---

## 📊 ORDER BY – raða niðurstöðum

```php
<?php
$query = $pdo->query("SELECT * FROM nemandi ORDER BY faeddur");
$nemendur = $query->fetchAll();
?>
```
