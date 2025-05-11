# Grunnatriði í PHP

## Breytur
- Allar breytur byrja á `$` tákninu.  
  Dæmi:
  ```php
  $nafn = "Jon";
  ```

## Úttak
- Notaðu `echo` til að prenta út texta eða gildi.  
  Dæmi:
  ```php
  echo "Halló heimur!";
  ```

- Notaðu punkt (`.`) til að tengja saman texta og breytur:
  ```php
  echo "Halló " . $nafn . "!";
  ```

## Seta skipana
- Allar skipanir enda á semíkommu `;`.
- Ekki þarf að setja semíkommu eftir slaufusvig `{}` í `if`, `else`, `elseif` eða `function`.

---

# Föll

- Föll eru skilgreind með `function`:
  ```php
  function heilsun($nafn) {
      return "Sæll, " . $nafn;
  }
  ```

- Skila gildi með `return`.
- Færibreytur eru settar á milli sviga `()`.

---

# Fylki (Arrays)

- Skilgreining fylkis:
  ```php
  $tölur = [1, 2, 3, 4];
  ```

- Notaðu `count()` til að telja stök í fylki:
  ```php
  echo count($tölur);
  ```

---

# Skilyrðissetningar (if)

```php
if ($gildi > 0) {
    // eitthvað gerist
} elseif ($gildi == 0) {
    // annað gerist
} else {
    // eitthvað annað gerist
}
```

---

# Lykkjur

## For-lykkja
```php
for ($i = 0; $i < 10; $i++) {
    // eitthvað gerist
}
```

## While-lykkja
```php
while ($i < 10) {
    // eitthvað gerist
    $i++;
}
```

## Foreach-lykkja
```php
foreach ($tölur as $tala) {
    // eitthvað gerist með $tala
}
```

# Lyklafylki (Associative Arrays) í PHP

## Skilgreining
- Í lyklafylki eru gildi vistuð með lykli frekar en tölulegum index.
```php
$notandi = [
    "nafn" => "Anna",
    "aldur" => 28,
    "netfang" => "anna@example.com"
];
```

## Aðgengi að gögnum
- Til að nálgast gildi notarðu lykilinn:
```php
echo $notandi["nafn"]; // Skilar "Anna"
```

## Breyta gildi
- Þú getur breytt gildi með því að vísa í lykilinn:
```php
$notandi["aldur"] = 29;
```

## Bæta við nýju pari
```php
$notandi["stadur"] = "Reykjavík";
```

## Foreach í gegnum lyklafylki
- Notaðu bæði lykil og gildi:
```php
foreach ($notandi as $lykill => $gildi) {
    echo $lykill . ": " . $gildi . "\n";
}
```

# Strengir í PHP

PHP býður upp á fjölda fölla til að vinna með strengi. Hér eru 5 algengar aðgerðir:

## 1. `strlen()` – Lengd strengs
- Skilar fjölda stafa í streng.
```php
$tekstur = "Halló heimur";
echo strlen($tekstur); // 12
```

## 2. `substr()` – Sækja hluta af streng
- Sækir hluta af streng frá gefinni byrjun og lengd (valfrjálst).
```php
$tekstur = "Halló heimur";
echo substr($tekstur, 6);       // "heimur"
echo substr($tekstur, 0, 5);    // "Halló"
```

## 3. `strtolower()` og `strtoupper()` – Lágstafir / hástafir
- Breytir öllum stöfum í streng í lágstafi eða hástafi.
```php
echo strtolower("Heimur"); // "heimur"
echo strtoupper("halló"); // "HALLÓ"
```

## 4. `strpos()` – Finna staðsetningu í streng
- Skilar staðsetningu fyrsta staks í streng (0-indexed), eða `false` ef ekki finnst.
```php
echo strpos("Halló heimur", "heimur"); // 6
```

## 5. `str_replace()` – Skipta út streng
- Skiptir öllum tilvikum af tilteknum hluta út fyrir annan.
```php
$nyr = str_replace("heimur", "veröld", "Halló heimur");
echo $nyr; // "Halló veröld"
```