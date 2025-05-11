# HLUTI 3: FORM  
## Glærur 1 – HTML form og samskipti við PHP

---

## 📝 Form – hvað og af hverju?

- Til að vista ný gögn í gagnagrunn frá vefsíðu (t.d. nýtt verkefni eða frétt) notum við `<form>` í HTML.
- `<form>` er HTML tag sem getur innihaldið t.d. `<input>`, `<button>` og fleiri tög.
- `<form>` sendir gögn frá vefsíðu yfir á server (PHP) sem getur vistað þau í gagnagrunn.

---

## 🧩 Grunnbygging forms

```html
<form action="save-task.php" method="post">
  ...
</form>
```

- `action`: skráin sem á að taka á móti gögnunum (t.d. PHP skrá).
- `method`: hvernig gögnin eru send (`GET` eða `POST`).

---

## 🔄 GET vs POST

- **GET**: Gögnin birtast í slóðinni.
- **POST**: Gögnin eru falin, oft notað þegar verið er að vista gögn.
- Regla:  
  - Notaðu **POST** til að **vista**  
  - Notaðu **GET** til að **ná í gögn**

---

## 🔡 `<input>` tag

- `<form>` virkar ekki nema það innihaldi `<input>` til að safna gögnum frá notanda.
- Textabox með `type="text"`:

```html
<input name="full-name" type="text" />
```

- `name` attribute ákvarðar nafnið á breytunni sem fer á server.

---

## ✅ Submit takki

- Notum `<button>` með `type="submit"` til að senda formið:

```html
<button type="submit">Submit</button>
```

- Þegar form með `GET` er sent, birtast gögnin í slóðinni:

```
http://localhost:8000/save-movie.php?titill=Deadpool
```

### Fullt formdæmi:

```html
<form action="save-movie.php" method="GET">
  <input name="titill" type="text" />
  <button type="submit">Submit</button>
</form>
```

---

## 🐘 PHP og formgögn

- Þegar formið sendir gögn á PHP skrá, notum við `$_GET` eða `$_POST` til að nálgast gögnin.

```php
<?php
echo $_GET["full-name"];
?>
```

- Athuga hvort breyta er til áður en hún er notuð:

```php
<?php
$titill = isset($_GET['titill']) ? $_GET['titill'] : '';
echo $titill;
?>
```

- Sjá allar breytur sem komu frá formi (debugging):

```php
<?php
die(var_dump($_GET));
?>
```
