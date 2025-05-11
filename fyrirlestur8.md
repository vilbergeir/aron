# HLUTI 3: FORM  
## Glærur 2 – Vista gögn í gagnagrunn með INSERT

---

## 🧾 INSERT í SQL

- Við getum vistað nýjar upplýsingar í gagnagrunn með `INSERT` skipun.

| id | description       | finished |
|----|-------------------|----------|
| 1  | Klára heimanám     | 0        |
| 2  | Elda kvöldmat      | 1        |

---

## 🏗️ SQL kóði til að búa til töflu

```sql
CREATE TABLE tasks (
  id int not null primary key auto_increment,
  description varchar(255),
  finished boolean
);
```

---

## ✍️ INSERT með `prepare` í PHP

```php
<?php
$data = [null, "Fara í búðina", 0];
$pdo->prepare("INSERT INTO tasks VALUES (?,?,?)")->execute($data);
?>
```

- Þá lítur taflan svona út:

| id | description     | finished |
|----|------------------|----------|
| 1  | Klára heimanám    | 0        |
| 2  | Elda kvöldmat     | 1        |
| 3  | Fara í búðina     | 0        |

---

## 📝 Gögn úr formi vistuð í gagnagrunn

### Formið í HTML

```html
<form action="save-task.php" method="post">
  <div>
    <label for="description">Description</label>
    <input type="text" id="description" name="description">
  </div>
</form>
```

### PHP kóði til að taka við gögnunum og vista í töflu

```php
<?php
$description = $_POST['description'];
$data = [null, $description, 0];
$pdo->prepare("INSERT INTO tasks VALUES (?,?,?)")->execute($data);
?>
```

---

## 🔁 Redirect eftir innsendingu

- Eftir að gögn hafa verið vistuð í gagnagrunninn í `save-task.php` viljum við fara aftur á síðuna með forminu (eða verkefnalistann).

- Notum `header("Location: ...")` til að færa notandann yfir á aðra síðu.

### Dæmi: `save-news.php`

```php
<?php
$description = $_POST['description'];
$data = [null, $description, 0];
$pdo->prepare("INSERT INTO tasks VALUES (?,?,?)")->execute($data);
header("Location: tasks.php");
?>
```
