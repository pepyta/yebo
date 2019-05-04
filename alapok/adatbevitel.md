# Adatbevitel

Adatbevitel alatt a Javaban most azt fogjuk érteni, ahogy a konzolba írunk szöveget és azt a a programunk képes beolvasni, eltárolni és feldolgozni.

A Java erre a `Scanner` nevű osztály biztosítja megoldásul.

## Scanner létrehozása

A Scanner osztályt példányosítani kell ahhoz, hogy használni tudjuk. A `Scanner` a `System.in` paraméterrel fog rendelkezni jelen esetünkben, hogy be tudja olvasni azt a bemenetet, amit a billentyűzeten adunk.

```java
// Scanner osztály példányosítása
Scanner bemenet = new Scanner(System.in);

// A példányosítás sorrendje:
// OsztályNeve változóNév = példányosítóUtasítás OsztályNeve(paraméter);
```

## Számok beolvasása

Számok beolvasásásra a `Scanner` osztály `nextInt()` metódusát tudjuk alkalmazni.

```java
// Scanner osztály példányosítása
Scanner bemenet = new Scanner(System.in);

// Kommunikáljunk a felhasználóval
System.out.println("Hány őzet számoltál meg útközben?");

// Majd hivatkozzunk a nextInt() metódusra
int őzek = bemenet.nextInt();
```

## Szöveg bekérése

A szövegek bekérésére a `Scanner` osztály `nextLine()` metódusa használható.

```java
// Scanner osztály példányosítása
Scanner bemenet = new Scanner(System.in);

// Kommunikáljunk a felhasználóval
System.out.println("Hogy hívnak?");

// Majd hivatkozzunk a nextLine() metódusra
String név = bemenet.nextLine();
```

## A `nextInt()` és `nextLine()` egymás utáni használata

{% hint style="danger" %}
A nextInt\(\) metódus rengeteg whitespace karaktert hagy maga után, ezért ha ugyanazzal az objektummal akarjuk bekérni, akkor csinálnunk kell egy nextLine\(\) hívást a tényleges bekérés előtt!
{% endhint %}

```java
// Scanner osztály példányosítása
Scanner bemenet = new Scanner(System.in);

// Kérdezzük meg az életkorát
System.out.println("Hány éves vagy?");

// Bemenet eltárolása
int kor = bemenet.nextInt();

// Eldobjuk a hibás sort
bemenet.nextLine();

// Kommunikáljunk a felhasználóval
System.out.println("Hogy hívnak?");

// Majd hivatkozzunk a nextLine() metódusra
String név = bemenet.nextLine();
```

