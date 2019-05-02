# Stringek és műveleteik

A Stringek a referencia típusú változók közé tartoznak, emiatt a változótípusokat nagy betűvel kezdjük. Ezekkel a változókkal rengeteg műveletet végezhetünk. Ezek közül ebben a cikkben megnézünk párat.

```java
// Így hozzuk létre általában a String típusú változót
String név = "Az én nevem";

// Így is hozhatunk létre, de felesleges
String állat = new String("Medve");
```

## Konkatenáció \(szövegösszefüggés\)

A Stringeket kiegészítését konkatenációnak nevezzük.

```java
// A konkatenációt legtöbbször így végezzük
String jeges = állat + " Jeges";

// De így is megtehetjük
String grizly = név.concat(" Grizly");
```

## Egyenlőség vizsgálata

Két Stringet nem egyszerűen dupla egyenlőségjellel vizsgáljuk, bár a Java újabb verziói tartalmazzák. Sokkal esztétikusabb és visszafelé kompatibilitást biztosít, ha az `equals`  metódust használjuk.

```java
// Mivel a jeges értéke "Medve Jeges", a grizly értéke pedig "Medve Grizly", ezért
// az else ágra fog térni.
if(grizly.equals(jeges)){
    System.out.printLn("A két medve megegyezik. Brumm-brumm!");
} else {
    System.out.printLn("Jaj, ne! A két medvét rossz ketrecbe raktuk be!");
}
```

## Karakter lekérdezése

Egy Stringben egy bizonyos pozíción lévő karaktert a `charAt` metódussal kérhetjük le. Ez a metódus egyetlen paramétert vár, ami egy index. Az indexek 0-tól indulnak és a hossz-1-ig tartanak. Ezért, ha az első karaktert akarjuk lekérni, akkor a 0-ra hivatkozunk, ha pedig az ötödik karaktert, akkot a 4-esre kell hivatkozni.

```java
// Új váltizó felvétele
String text = "Hello World";

// 'o' betű kiíratása
System.out.printLn(text.charAt(4));
```

## Összehasonlítás

Két Stringet lexikogrfikusan összehasonlíthatunk. Az összehasonlításban csakis az angol ABC karaktereit rendezi le szabályosan, tehát ha a szöveg tartalmaz magyar karaktert, akkor azt már hibásan rendezi.

A metódus negatív visszatérési értéket ad, ha az angol ABC-ben a szó hátrébb helyezkedik el, nullát, ha megegyezik és pozitívat, ha előrébb van az alap String, mint amit paraméterként kap.

```java
// Új változók felvétele
String egy = "foo";
String kettő = "bar";

// Negatív értéket fog kiírni a képernyőre.
System.out.printLn(egy.compareTo(bar));
```

{% hint style="warning" %}
A `compareTo` és az `equals` külön feladatra valók és nem használható a `compareTo`nullás visszatérési értéke egyezés vizsgálatára.
{% endhint %}

## Szöveg kicserélése

Gyakran fordul elő, hogy az eredeti Stringben olyan karakterek találhatóak, amik nekünk nem felelnek meg, ezért azokat ki kell cserélnünk. Erre a Java a `replace`, `replaceFirst`és `replaceAll` metódust biztosítja.

A `replace`egyetlen féle karaktert cserél ki az adott Stringben egy másik adott karakterre.

A `replaceFirst` és `replaceAll` egy Stringben az adott regex-re \(reguláris kifejezés, regular expression\) illeszkedő részt cserél ki egy Stringre.

{% hint style="info" %}
A regex tulajdonságokat ki lehet használni rengeteg esetben, ezek közül a leggyakoribb, hogy egy Stringből a számokat vagy a betűket kell kicserélni.
{% endhint %}

```java
// Egy olyan String, ami tartalmaz 'á' karaktereket
String rosszString = "Egy kedves ember szereti a mákos gubát.";

// Gyakori, hogy nem használhatjuk az ékezetes betűket
// a karakterkódolás miatt ezért mi kicseréljük ezeket
String jóSzöveg = rosszString.replace('á', 'a');
```

```java
// Egy bemeneti String, aminek csak számokat kéne tartalmaznia
String bemenet = "Jani 378 szelet kenyeret evett meg ebben az évben";

// Ahhoz hogy megkapjuk, hogy milyen számot kaptunk ki kell cseréljük
// az összes szöveget, ami nem szám egy üres karakterre.
String szám = bemenet.replaceAll("[^0-9]", "");

// Így ha kiíratjuk, akkor csak 378-at fogunk kapni.
System.out.printLn(szám);
```

## Felesleges karakterek eltüntetése

Előfordulhat, hogy a felhasználó által beírt szöveg tartalmazhat felesleges whitespaceket. Azokat a nem nyomtatható karaktereket nevezzük ennek, amik a szöveg elején vagy végén helyezkednek el és nem befolyásolja a megjelenítést semmilyen formában.

```java
// Egy felesleges String, ami felesleges karakterket tartalmaz
String hibás = "    Ma napos időnk van   \r \n          ";

// A szövegből eldobjuk a felesleges karaktereket.
// A /r és /n karakter az az új sor kezdését jelenti
// különböző operációs rendszereken.
System.out.printLn(hibás.trim()); 
```



