# Elemi algoritmusok

## Eldöntés

Ezzel a módszerrel dönthetjük el, hogy egy adott tömb tartalmaz-e egy adott elemet.

1. Felveszünk egy változót, ami tárolja, hogy tartalmazza-e. Alapértéke: `false`
2. Megvizsgoljuk egyesével az összes elemet.
3. Megvizsgáljuk az utolsó elemet, hogy megegyezik-e. 
4. Ha igen, akkor a változó értékét átálítjuk `true`-ra.

```java
// Felveszünk egy tömböt, amelybe elemeket rakunk
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Felvesszük a változót, amiben tároljuk, hogy tartalmazza-e
boolean tartalmaz = false;

// A vizsgált elemet egy változóban eltároljuk
int feltétel = 6;

// Végigmegyünk a tömb összes elemén
for(int elem: vektor){
    if(elem == feltétel){
        // Ha tartalmazza, akkor átállítjuk az értékét
        tartalmaz = true;
        
        // Nem kell több elemet vizsgálni, mert már találtuk egy olyat.
        break;
    }
}
```

## Megszámlálás

Eléggé beszédes a neve. Egy adott tömbben megszámlálja, hogy adott elemből hány darab található.

1. Felveszünk egy változót, amiben tároljuk a darabszámot.
2. Végigmegyünk a tömb összes elemén.
3. Ha megegyezik a feltétellel, akkor a darabszámot növeljük eggyel.

```java
// Felveszünk egy tömböt, amelybe elemeket rakunk
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Felvesszük a változót, amiben tároljuk a darabszámot
int darab = 0;

// A vizsgált elemet egy változóban eltároljuk
int feltétel = 3;

// Végigmegyünk az összes elemen
for(int elem: vektor){
    if(elem == feltétel){
        // Ha megfelel a feltételnek, akkor növeljük a darabszámot
        darab++;
    }
}
```

## Keresés

Megkeressük, hogy egy adott tömbben hanyas index alatt található az adott érték. Ha nem tartalmazza, akkor negatív értékkel kell, hogy dolgozzunk, mert így tudjuk, hogy nincs ilyen.

1. Változó felvétele, amiben tároljuk az elem helyét \(alapérték: `-1`\).
2. Végigmegyünk az összes elemen \(indexelt ciklussal\).
3. Ha megegyezik, akkor a változónkát átállítjuk az adott indexre.

Ezzel a módszerrel az utolsó elemet határozzuk meg, ami kielégíti a feltételt.

```java
// Felveszünk egy tömböt, amelybe elemeket rakunk
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Felvesszük a változót, amiben tároljuk az elem helyét
int hely = -1;

// A vizsgált elemet egy változóban eltároljuk
int feltétel = 3;

// Végigmegyünk az összes elemen
for(int i = 0; i < vektor.length; i++){
    // Ha megegyezik, akkor beállítjuk a hely megjelölésére
    if(vektor[i] == feltétel){
        hely = i;
    }
}
```

Ha az első elemet akarjuk meghatározni, akkor a feltétel vizsgálatba helyezzünk be egy `break` parancsot és így a legelső elemet fogja beállítani.

## Buborék rendezés

A buborák rendezés a leglassabb rendezés az összes közül. A buborék rendezés úgy működik, hogy minden elemet összehasonlít mindegyikkel, ezáltal ha a korábban lévő kisebb mint az utána lévő, akkor megcseréli azt.

Hatékonysága:  $$O(n) = n^2$$ .

{% hint style="info" %}
A buborék rendezésnél sokkal egyszerűbb, ha az Arrays.sort parancsot használjuk. A kód ezáltal sokkal követhetőbb és gyorsabb is a program. Ennek hatékonysága: $$O(n) = log2(n)$$ 
{% endhint %}

```java
// Felveszünk egy tömböt, amelybe elemeket rakunk
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Végigmegyünk a tömb összes elemén
for(int i = 0; i < vektor.length; i++){
    // Minden elemet mindegyikkel összehasnlítjuk
    for(int j = 0; j < vektor.length; j++){
        // Ha nagyobb, akkor megcseréljük
        if(vektor[i] < vektor[j]){
            int temp = vektor[i];
            vektor[i] = vektor[j];
            vektor[j] = temp;
        }
    }
}

// Vagy ha lusták vagyunk ennyivel is megoldhatjuk
Arrays.sort(vektor);
```

## Összefuttatás

Két tömb elemeit összefuttathatjuk és ezáltal lesz egy nagy tömbünk, ami mind két tömb elemeit tartalmazza.

1. Létrehozunk egy új tömböt, aminek a nagysága annyi mint a két tömbbé összeadva.
2. Létrehozzuk a strázsa nevű változót, ami megmutatja hány elem van már benne és hova lehet tenni a következő elemet az új tömbbe.
3. Végigmegyünk az első tömbbön és hozzáadjuk
4. Ugyanezt megtesszük a második tömbbel is

```java
// Létrehozzuk a két tömbünket
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };
int [] másik = { 1, 6, 3, 5, 9, 10, 4 };

// Létrehozzuk az új tömböt
int [] tömb = new int[vektor.length + másik.length];

// Felvesszük a strázsa nevű változót
int strázsa = 0;

// Hozzáadjuk az első tömb elemeit
for(int elem: vektor){
    tömb[strázsa++] = elem;
}

// Majd hozzáadjuk a második tömb elemeit is
for(int elem: másik){
    tömb[strázsa++] = elem;
}
```

## Kiválogatás I.

Egy új tömbbe kiválogatjuk a feltételnek megfelelő elemeket.

1. Megszámoljuk hány ilyen elem létezik, ami kielégíti a feltételt.
2. Létrehozunk egy új tömbböt ilyen hosszúsággal.
3. Felvesszük a strázsát, ami megmutatja hova rakhatunk új elemet.
4. Feltöltjük az új tömböt.

```java
// Létrehozzuk a tömbünket
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Eltároljuk a feltételt egy változóban
int feltétel = 3;

// Megszámoljuk hány elem van ami kielégíti a feltételt
int darab = 0;
for(int elem: vektor){
    if(elem == feltétel){
        darab++;
    }
}

// Létrehozzuk az új tömböt
int [] tömb = new int[darab];

// Felvesszük a strázsa nevű változót
int strázsa = 0;

// Feltöltjük az új tömböt elemekkel
for(int elem: vektor){
    if(elem == feltétel){
        tömb[strázsa++] = elem;
    }
}
```

## Kiválogatás II.

Ezt az algoritmust akkor használjuk, ha nem tudjuk, hogy a tömb hány ilyen elemet tartalmaz.

1. Létrehozunk egy új tömböt az eredeti méretével.
2. Felvesszük a strázsa nevű változót.
3. Ha egyezik, akkor a strázsa helyére beillesztjük az elemet.

```java
// Létrehozzuk a tömbünket
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Létrehozzuk az új tömböt
int [] tömb = new int[vektor.length];

// Felvesszük a strázsa nevű változót
int strázsa = 0;

// Hozzáadjuk az első tömb elemeit
for(int elem: vektor){
    // Minden páros elemet átmásolunk
    if(elem % 2 == 0){
        tömb[strázsa++] = elem;
    }
}
```

## Kiválogatás III.

A haramdik kiválogatást akkor használjuk, ha csak egyedi elemeket akarunk átmásolni, amik kielégítik az adott feltétel.

1. Létrehozunk az eredeti tömb méretével megegyező tömböt.
2. Felvesszük a strázsa nevű változót.
3. Végigmegyünk az eredeti tömb összes elemén.
4. Felveszünk egy tartalmazza-e változót.
5. Ha kielégíti a feltételt, akkor végig megyünk az új tömbünk és megnézzük a tartalmazását.
6. Ha nincs benne, akkor hozzáadjuk és növeljük a strázsát.

```java
// Létrehozzuk a tömbünket
int [] vektor = { 3, 2, 6, 12, 3, 4, 9, 10 };

// Létrehozzuk az új tömböt
int [] tömb = new int[vektor.length];

// Felvesszük a strázsa nevű változót
int strázsa = 0;

// Végigmegyünk a tömb összes elemén
for(int elem: vektor){
    // Megvizsgáljuk, hogy kielégíti-e a feltételt
    // A jelenlegi feltétel a árommal való oszthatóság
    if(elem % 3 == 0){
        // Megvizsgáljuk, hogy az új tömb tartalmazza-e már
        boolean tartalmaz = false;
        for(int i = 0; i < strázsa; i++){
            if(tömb[i] == elem){
                tartalmaz = true;
            }
        }
         
        // Ha nem, akkor hozzáadjuk  
        if(!tartalmaz){
            tömb[strázsa++] = elem;
        }
    }
}
```

