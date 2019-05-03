# Tömbök és műveleteik

A tömbök azonos típusú elemek tárolására szolgáló megoldás Javaban. 

{% hint style="danger" %}
A tömbök fix nagyságúak és azonos elemek tárolására alkalmas csak. Amennyiben ezek a feltételek nem felelnek meg neked, akkor nézd meg a Gyűjtemények szekciót!
{% endhint %}

## Tömbök létrehozása

A tömbök létrehozásával meghatározzuk a tömb maximális méretét. A tömböket úgy kell elképzelni, mintha egy szekrény lenne, aminek a fiókjaiban tárolhatunk dolgokat, de azokból mind egyfélének kell lennie. Mint egy szekrény, amibe csak tollakat rakhatunk.

```java
// A tömb létrehozásánál példányosítás történik a "new" jelző miatt
int [] vektor = new int[10];

// A tömb létrehozásának a sorrendje:
// típus tömbjel tömb_neve = példányosító_utasítás típus_újra[méret];
```

## Kezdőértékkel feltöltés

A tömböket feltölthetjük statikusan és dinamikusan. A statikus feltöltés során nem kell beírni a tömb létrehozására szolgáló utasítást, a Java elrejtve, de megcsinálja nekünk akkor is.

### Statikus feltöltés

A statikus feltöltésnek két módja van. Ha előre megírt elemekkel akarjuk megölteni a tömböt vagy, ha minden elem ugyan az.

```java
// Előre megadott elemekkel történő feltöltés
boolean [] reggelizik = { false, true, true, false, false, true };

// Ebben az esetben egy hat elemű boolean tömböt hozunk létre,
// amiket feltöltünk egyesével ezekkel az elemekkel.
```

```java
// Ha minden elem megegyezik sokkal egyszerűbb, ha
// egy ciklussal végigmegyünk a tömbön és feltöltjük.

// Tömb létrehozása
int [] hatosok = new int[6];

// Ciklussal történő feltöltés
for(int hatos: hatosok){
    hatos = 6;
}
```

### Dinamikus feltöltés

A dinamikus feltöltés során egy bizonyos módszerrel meghatározzuk minden elemnek az értékét és azt adjuk neki értéknek. Ilyenkor kötelező ciklussal végigmenni a tömbön.

```java
// Tömb létrehozása
int [] lottószámok = new int[5];

// Majd feltöltjük egy ciklus segítségével
for(int nyerő: lottószámok){
    // Ezzel a módszerrel egy egész számot generálunk
    // [1; 90] tartományban. Ennek a módszere:
    // (int)(Math.random()*(max-min+1)+min)
    nyerő = (int)(Math.random()*90+1);
}
```

## Elemek elérése

A tömb elemeire az indexei alapján hivatkozhatunk, amit egy kapcsos zárójelbe kell beírnunk.

```java
// Tömb létrehozása
int [] vektor = { 4, 7 };

// Két elemű tömbben azt akarom, hogy a nagyobb legyen előrébb
if(vektor[0] < vektor[1]){
    // Megcseréljük a két elemet egy segédváltozóval
    int temp = vektor[0];
    vektor[0] = vektor[1];
    vektor[1] = temp;
}
```

A tömbök elemei teljes értékű változóként funkcionálnak, ha csak egyetlen elemre hivatkozunk. Ennek ha értéket adunk, akkor a tömbben is meg fog változni.

## Tömb mérete

A tömb méretére a `tömb.length` tulajdonsággal hivatkozunk.

{% hint style="info" %}
A tömbnek a nagysága egy tulajdonsága, nem változhat, ezért nem metódusra fogunk hivatkozni, hanem a közvetlen tulajdonságára, ezért a zárójeleket nem szabad kiírni!
{% endhint %}

```java
// Tömb létrehozása
String [] osztály = new String[35];

// A tömb az osztályban tanuló emberek neveit adja meg
// 35-öt fog visszaadni, mivel ekkora memóriaterületet
// foglaltunk le a tömbünknek.
System.out.printLn("Az osztályba "+osztály.length+" tanuló jár");
```

