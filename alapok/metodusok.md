# Metódusok

A metódusok olyan feladatot látnak el, hogy hivatkozhatunk rájuk, ha valamit meg kell csinálnunk és azt a kódunkba nem kell töbször beleírni. Ezáltal a kódunk sokkal letisztultabb lesz.

A metódusokat két nagy csoportja osztjuk:

1. `main` melletti metódusok
2. Osztálymetódusok

Minden metódusnak van egy visszatérési értéke és paraméter listája. A visszatérési értéknek mindenképpen változónak kell lennie \(lehet primitív vagy referencia\) vagy pedig `void`, ami nem ad vissza értéket, csak csinál valamit.

A paraméter listában pedig típus deklaráció történik, tehát meghatározzuk a változó nevét és annak a típusát. A paraméter listában megadott primitív típusú változók megkapják a paraméterek értékét, de nem tudják beállítani a paraméterként kapott változó értékét. Amennyiben a metódussal akarjuk befolyásolni, akkor a változók referencia változatait kell használjuk \(pl.: int helyett Integert használunk\).

## A `main` melletti metódusok

A main melletti metódusok mindig `static`-kal kezdődnek, mivel a `main`-t nem tudjuk példányosítani és ezért nem kell még a `main`-t sem megjelölni, automatikusan tudja a Java, hogy arra hivatkozunk.

```java
public class metodusok{
    public static void main(String[] args) {
        // Létrehozunk egy tömböt
        int [] vektor = { 2, 4, 1, 8, 3, 9 };
        
        // A mainen belül hivatkozunk a metódusunkra
        System.out.printLn("A tömb legkisebb eleme "+min(vektor)+".");
        
        // A programunk legkisebb elemként 1-et fog kiírni.
    }
    
    // Ezzel a metódussal meghatározzuk egy tömb
    // legkisebb elemét.
    
    // A tömb static-kal kezdődik, visszatérési értéke int.
    // Paraméterként egy tömböt kap. Mivel ez egy tömb,
    // ezért referencia típus, tehát lehet a metóduson
    // belülről is akár módosítani értékét.
    static int min(int [] tömb){
        // Feltételezzük, hogy az első elem a legkisebb
        int result = tömb[0];
        
        // Végigmegyünk az összes elemen
        for(int i = 0; i < tömb.length; i++){
            // Ha találunk kisebbet azt állítjuk be
            if(tömb[i] < result){
                result = tömb[i];
            }
        }
        
        // Miután végigmentünk az összesen visszaadjuk
        return result;
    }
}
```



