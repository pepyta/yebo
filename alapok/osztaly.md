# Osztályok

Az osztályok \(`Class`\) az objektum-orientált programozás alapjait jelentő elemek. Lényegük, hogy azokat az adatokat és a velük végezhető műveleteket, amik egy elemre jellemzőek egy egységben tároljuk.

![](../.gitbook/assets/hun_1_misrhzvzvu-y0ubxo2thhw%20%282%29.png)

Az osztályokat a gyakorlatban úgy kell elképzelni, mintha valamit be kéne mutani. Egy pólóra a méretével és a színével tudod jellemezni, míg egy focistát a mezszámával, a nevével és a csapatával.

## Osztályok létrehozása

Az osztályoknak minden esetben legalább két metódussal kell rendelkezniük: egy konstruktorral és egy destruktorral. Szerencsére a Java nekünk a destruktort mindig elkészíti, de a konstruktor a mi feladatunk.

A konstruktor feladata a változó nevek és típusainak megadása \(deklaráció\) és azoknak értéket adni. A konstruktort könnyű felismerni, mivel úgy néz ki, mint egy metódus, annyi különbséggel, hogy nincs visszatérési értéke és megegyezik a neve az osztályéval.

```java
public class Osztalyok {
    public static void main(String[] args) {
        // Most nem ide fogjuk írni a ódunkat
    }
    
}

// Létrehozunk egy új osztályt Macska néven
// Az osztály neve mindig nagy betű
class Macska {
    // Deklaráljuk a változókat
    private int hangulat;
    private int éhség;
    private int energia;

    // A konstruktorban paraméterként megkapjuk a változók értékét
    // és azokat az értékeket beállítjuk a tagadatainknak.
    public Macska(int hangulat, int éhség, int energia) {
        // A this része a kódnak elhagyható, csak 
        // a kód szépsége miatt rakjuk oda.
        this.hangulat = hangulat;
        this.éhség = éhség;
        this.energia = energia;
    }
    
    // Létrehozunk egy nyávogás nevű metódust
    // A static itt már elhagyható
    private void nyavogas(){
        System.out.println("Miáu!");
    }
}
```

## Példányosítás

Az osztályból objektumokat hozhatunk létre, amikkel később dolgozhatunk. Ezt a folyamatot példányosításnak nevezünk, amit a `new` parancs intéz el nekünk.

```java
public class Osztalyok {
    public static void main(String[] args) {
        // Most létrehoztunk egy "sanyi" nevű objektumot,
        // aminek adtunk kezdő értéket.
        Macska sanyi = new Macska(100, 0, 100);
    }
    
}
```

## Tömb készítése

Az osztályokból, akár más típusú változókból tömböket hozhatunk létre, amik ugyanúgy működnek, mintha más típusú változókból jöttek volna létre.

```java
public class Osztalyok {
    public static void main(String[] args) {
        // Itt létrehozzuk a tömböt, amiknek a
        // fiókjaira már a tanult módon hivatkozhatunk.
        Macska [] menhely = {
             new Macska(100, 0, 100),
             new Macska(10, 10, 40),
             new Macska(70, 0, 60)
        };
    }    
}
```

## Módosítók

| Módosító neve | Mit csinál |
| :--- | :--- |
| public | Az osztályon kívülről is elérhetővé teszi a metódust vagy változót. |
| private | Csakis az osztály saját metódusai hivatkozhatnak erre a metódusra vagy módosíthatják ezt a változót. |
| static | Osztálypéldány nélkül elérhetővé teszi a metódust a használatra. Ilyenkor az osztály nevére kell hivatkozni. |
| final | Egy olyan változót vagy metódust jelent, amit már nem lehet felülírni. |
| abstract | Nem példányosítható. Azért hozzuk létre, hogy készőbb leszármaztassunk belőle. |

```java
class Macska {
    ...
    // Az állatok neve nem gyakran változik
    final String név;
    
    // A korábban mutatott alvás funkció
    public void alvas(){
        energia++;
        éhség++;
    }
}
```

## Források

* [A macskás illusztráció angolul](https://cdn-images-1.medium.com/max/2400/1*mISRhzvzvU-y0uBXo2thhw.png)

