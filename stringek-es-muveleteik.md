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





