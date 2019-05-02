---
description: A Javaban található alapvető változótípusok és utasításaik.
---

# Változótípusok és utasításaik

## Milyen változótípusok léteznek?

A Javaban alapvetően két kategóriára oszthatjuk a változókat.

### Primitív típusok

A primitív változók számokat tárol különböző változatokban. Minden primitív változónak van egy referencia változata \(zárójelben található\), amelynek a szerepéről később esik szó.

* **int** \(Integer\): egész számokat tároló változótípus. 
* **double** \(Double\): tört számokat tároló változótípus.
* **char** \(Character\): egyetlen karaktert tároló változótípus.
* **boolean** \(Boolean\): logikai értéket tároló változótípus.
* **float** \(Float\): frakcionális számokat tároló változótípus.
* **long** \(Long\): az intnél hosszabb egész számokat is tárol. \(-9,223,372,036,854,775,808-től 9,223,372,036,854,775,807-ig\)

A primitív típusú változókkal a következő műveletek végezhetőek:

| Művelet | Jelölése | Mit csinál? |
| :--- | :--- | :--- |
| Értékadás | + | Két számot ad össze. |
| Kivonás | - | Kit számot von ki. |
| Egész osztás | / | Két int típusú változó elosztásakor végzett művelet. Mindig egészértéket ad vissza, a tört részét eldobja a sima osztásnak. \(pl.: 7/5 = 1\) |
| Tört osztás | % | Két int típusú változó osztási maradékát adja meg, amely mindig egész szám. \(pl.: 7/5 = 2\) |
| Szorzás | \* | Két számot szoroz össze. |

### Referencia típusok

A referencia típusú változókat később osztály \(Class\) néven fogjuk emlegetni. Ezekről az elemekről majd a későbbiekben, az Osztályok rész alatt lesz szó.



