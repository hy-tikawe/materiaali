---
title: Kurssin arvostelu
permalink: /arvostelu/
---

# Kurssin arvostelu

Tälle sivulle on koottu asiat, jotka kurssin ohjaaja käy läpi työsi arvostelussa.

Sovelluksesta on mahdollista saada 0–100 pistettä. Kurssin hyväksytty suoritus vaatii, että saat vähintään 50 pistettä. Kurssin arvosana lasketaan näin:

* 50–59 pistettä: arvosana 1
* 60–69 pistettä: arvosana 2
* 70–79 pistettä: arvosana 3
* 80–89 pistettä: arvosana 4
* 90–100 pistettä: arvosana 5

Lisäksi jokaisesta tähdellä (*) merkitystä vaatimuksesta tulee saada vähintään yksi piste, jotta kurssista saa suorituksen.

Lisätietoa teknisistä vaatimuksista on [teknisessä tarkastuslistassa](../lista).

<style>
table {display: table; width:100%;}
</style>

### Sovelluksen perusvaatimukset (7 p)

| Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen | 1 p | * |
| Käyttäjä pystyy lisäämään, muokkaamaan ja poistamaan tietokohteita | 1 p | * |
| Käyttäjä näkee sovellukseen lisätyt tietokohteet | 1 p | * |
| Käyttäjä pystyy etsimään tietokohteita hakusanalla tai muulla perusteella | 1 p | * |
| Käyttäjäsivu näyttää tilastoja ja käyttäjän lisäämät tietokohteet | 1 p | * |
| Käyttäjä pystyy valitsemaan tietokohteelle yhden tai useamman luokittelun | 1 p | * |
| Käyttäjä pystyy lähettämään lisätietoa tietokohteeseen | 1 p | * |


### Tekniset perusvaatimukset (8 p)

| Sovellus toteutettu kurssimateriaalin mukaisesti | 1 p | * |
| Sovellus on toteutettu Pythonilla käyttäen Flask-kirjastoa | 1 p | * |
| Sovellus käyttää SQLite-tietokantaa | 1 p | * |
| Kehitystyössä on käytetty Gitiä ja GitHubia | 1 p | * |
| Sovelluksen käyttöliittymä muodostuu HTML-sivuista | 1 p | * |
| Sovelluksessa ei ole käytetty JavaScript-koodia | 1 p | * |
| Tietokantaa käytetään suoraan SQL-komennoilla (ei ORMia) | 1 p | * |
| Kirjaston `flask` lisäksi käytössä ei muita erikseen asennettavia kirjastoja | 1 p | * |

Kaikki nämä vaatimukset täyttyvät, jos toteutat sovelluksen kuten kurssimateriaalissa ja esimerkkisovelluksessa.

### Toimivuus ja käytettävyys (15 p)

| Käyttäjän yleiskokemus sovelluksen toimivuudesta | 5 p | |
| Käyttäjän yleiskokemus sovelluksen käytettävyydestä | 5 p | |
| Käyttäjän lähettämässä tekstissä rivinvaihdot näkyvät selaimessa | 1 p | |
| Kuvissa käytetty `alt`-attribuuttia (jos sovelluksessa kuvia) | 1 p | |
| Lomakkeissa käytetty `label`-elementtiä | 1 p | |
| CSS:n avulla toteutettu ulkoasu | 2 p | |

### Versionhallinta (10 p)

| Kehitystyön aikana on tehty commiteja säännöllisesti | 1 p | * |
| Commit-viestit on kirjoitettu englanniksi | 1 p | |
| Commitit ovat hyviä kokonaisuuksia ja niissä on hyvät viestit | 5 p | |
| Versionhallinnassa ei ole sinne kuulumattomia tiedostoja | 1 p | |
| Tiedosto `README.md` antaa hyvän kuvan sovelluksesta | 2 p |

### Ohjelmointityyli (15 p)

| Yleiskuva koodin laadusta (selkeys, luettavuus ja tyyli) | 5 p | |
| Sisennyksen leveys on neljä välilyöntiä | 1 p | |
| Koodi on kirjoitettu englanniksi | 1 p | |
| Muuttujien ja funktioiden nimet muotoa `total_count` (ei `totalCount`) | 1 p | |
| Merkkijonoissa käytetty aina joko `'` tai `"` | 1 p | |
| Välit oikein `=`-merkin ympärillä | 1 p | |
| Välit oikein `,`-merkin ympärillä | 1 p | |
| Ei koodia tyyliin `if success return True else return False` | 1 p | |
| Jos funktio palauttaa arvon, tulee olla useita mahdollisia palautusarvoja | 1 p | |
| Ei sulkeita `if`- ja `while`-rakenteiden ehtojen ympärillä | 1 p | |
| Ei ehtoja tyyliin `result == None` ja `result is None` | 1 p | |

Vinkki: Pystyt tarkastamaan monet yllä olevat asiat [Pylint-työkalun](../pylint) avulla

### Tietokanta-asiat (15 p)

| Taulut ja sarakkeet on nimetty englanniksi | 1 p | |
| Taulut ja sarakkeet on nimetty hyvin | 3 p | |
| Käytetty `REFERENCES`-määrettä, kun viittaus toiseen tauluun | 1 p | |
| Käytetty `UNIQUE`-määrettä, kun tulee olla eri arvo joka rivillä | 1 p | |
| Ei kyselyjä muotoa `SELECT *` | 1 p | |
| Pitkät SQL-komennot jaettu usealle riville | 1 p | |
| Kaikki tiedot haetaan yhdellä SQL-kyselyllä, jos järkevästi mahdollista | 3 p | |
| Koodissa ei tehdä asioita, jotka voi mielekkäästi tehdä SQL:ssä | 3 p | |
| Käytetty `try`/`except` SQL-komennon ympärillä vain aiheellisesti | 1 p | |

### Sovelluksen turvallisuus (20 p)

| Salasanat tallennetaan tietokantaan asianmukaisesti | 1 p | * |
| Käyttäjän oikeus nähdä sivun sisältö tarkastetaan | 5 p | * |
| Käyttäjän oikeus lähettää lomake tarkastetaan | 5 p | * |
| Käyttäjän syötteet tarkastetaan ennen tietokantaan lisäämistä | 3 p | * |
| SQL-komennoissa käytetty parametreja | 2 p | * |
| Sivut muodostetaan sivupohjien kautta | 2 p | * |
| Lomakkeissa on estetty CSRF-aukko | 2 p | * |

Jokaisessa kohdassa pistemäärä riippuu siitä, miten kattavasti asia on otettu huomioon sovelluksen koodissa.

### Suuren tietomäärän käsittely (5 p)

| Sovellusta testattu suurella tietomäärällä ja raportoitu tulokset | 3 p | |
| Sovelluksessa käytössä tietokohteiden sivutus | 1 p | |
| Tietokantaan lisätty indeksi, joka nopeuttaa suuren tietomäärän käsittelyä | 1 p | |

Sopiva tapa raportoida tulokset on lisätä tiedosto `seed.py` repositorioon ja kirjoittaa tiedostoon `README.md` selostus sovelluksen toiminnasta suurella tietomäärällä.

### Vertaisarviointi ja palaute (5 p)

| Ensimmäinen vertaisarviointi annettu | 1 p | * |
| Ensimmäinen vertaisarviointi tehty kattavasti | 1 p | |
| Toinen vertaisarviointi annettu | 1 p | * |
| Toinen vertaisarviointi tehty kattavasti | 1 p | |
| Kurssipalaute annettu | 1 p | |

Kurssin vastuuhenkilö saa palautejärjestelmästä listan opiskelijoista, jotka ovat antaneet palautteen. Järjestelmästä ei näe, kuka on antanut tietyn palautteen.
