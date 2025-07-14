---
title: Kurssin arvostelu
permalink: /arvostelu/
---

# Kurssin arvostelu

Tälle sivulle on koottu asiat, jotka kurssin ohjaaja käy läpi työsi arvostelussa.

Jokaisen kriteerin kohdalla on ilmoitettu, missä kurssin arvosanoissa vaaditaan, että kyseinen kriteeri toteutuu. Esimerkiksi:

* 1--5 tarkoittaa, että hyväksytyn sovelluksen tulee täyttää tämä kriteeri, koska se vaaditaan kaikissa arvosanoissa 1--5.
* 4--5 tarkoittaa, että tämä kriteeri vaaditaan arvosanoissa 4--5. Jos sovellus ei täytä tätä kriteeriä, arvosana on enintään 3.
* 5 tarkoittaa, että tämä kriteeri vaaditaan arvosanassa 5.

Kurssin arvostelu perustuu siihen, miten tällä sivulla ilmoitetut kriteerit täyttyvät lopullisessa sovelluksessa.

<style>
table {display: table; width:100%;}
</style>

### Sovelluksen perusvaatimukset

| Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen | 1--5 |
| Käyttäjä pystyy lisäämään, muokkaamaan ja poistamaan tietokohteita | 1--5 |
| Käyttäjä näkee sovellukseen lisätyt tietokohteet | 1--5 |
| Käyttäjä pystyy etsimään tietokohteita hakusanalla tai muulla perusteella | 1--5 |
| Käyttäjäsivu näyttää tilastoja ja käyttäjän lisäämät tietokohteet | 1--5 |
| Käyttäjä pystyy valitsemaan tietokohteelle yhden tai useamman luokittelun | 1--5 |
| Käyttäjä pystyy lisäämään tietokohteeseen toissijaisia tietokohteita | 1--5 |

Sovelluksen perusvaatimukset on kuvattu tarkemin [aloitussivulla](../aloitus).

### Tekniset perusvaatimukset

| Sovellus toteutettu kurssimateriaalin mukaisesti | 1--5 |
| Sovellus toteutettu Pythonilla käyttäen Flask-kirjastoa | 1--5 |
| Sovellus käyttää SQLite-tietokantaa | 1--5 |
| Kehitystyössä käytetty Gitiä ja GitHubia | 1--5 |
| Sovelluksen käyttöliittymä muodostuu HTML-sivuista | 1--5 |
| Sovelluksessa ei ole käytetty JavaScript-koodia | 1--5 |
| Tietokantaa käytetään suoraan SQL-komennoilla (ei ORMia) | 1--5 |
| Kirjaston `flask` lisäksi käytössä ei muita erikseen asennettavia kirjastoja | 1--5 |

### Toimivuus ja käytettävyys

| Sovelluksen perustoiminnot toimivat | 1--5 |
| CSS:n avulla toteutettu ulkoasu (itse tehty, ei CSS-kirjastoa) | 3--5 |
| Sovellusta on helppoa ja loogista käyttää | 4--5 |
| Käyttäjän lähettämässä tekstissä rivinvaihdot näkyvät selaimessa | 5 |
| Kuvissa käytetty `alt`-attribuuttia (jos sovelluksessa kuvia) | 5 |
| Lomakkeissa käytetty `label`-elementtiä | 5 |

### Versionhallinta (10 p)

| Kehitystyön aikana on tehty commiteja säännöllisesti | 1--5 |
| Commit-viestit on kirjoitettu englanniksi | 1--5 |
| Versionhallinnassa ei ole sinne kuulumattomia tiedostoja | 3--5 |
| Commitit ovat hyviä kokonaisuuksia ja niissä on hyvät viestit | 4--5 |
| Tiedosto `README.md` antaa hyvän kuvan sovelluksesta | 4--5 |

Tarkempaa tietoa vaatimuksista on [teknisessä tarkastuslistassa](../lista).

### Ohjelmointityyli (15 p)

| Koodi on kirjoitettu englanniksi | 1--5 |
| Muuttujat ja funktiot nimetty kuvaavasti | 4--5 |
| Sisennyksen leveys on neljä välilyöntiä | 4--5 |
| Koodissa ei ole liian pitkiä rivejä | 4--5 |
| Muuttujien ja funktioiden nimet muotoa `total_count` (ei `totalCount`) | 4--5 |
| Välit oikein `=`- ja `,`-merkkien ympärillä | 4--5 |
| Ei ylimääräisiä sulkeita `if`- ja `while`-rakenteissa | 4--5 |

Tarkempaa tietoa vaatimuksista on [teknisessä tarkastuslistassa](../lista).

Vinkki: Pystyt tarkastamaan monet yllä olevat asiat [Pylint-työkalun](../pylint) avulla

### Tietokanta-asiat (15 p)

| Taulut ja sarakkeet on nimetty englanniksi | 1--5 |
| Taulut ja sarakkeet on nimetty kuvaavasti | 3--5 |
| Käytetty `REFERENCES`-määrettä, kun viittaus toiseen tauluun | 3--5 |
| Ei kyselyjä muotoa `SELECT *` | 5 |
| Kaikki tiedot haetaan yhdellä SQL-kyselyllä, jos järkevästi mahdollista | 5 |
| Koodissa ei tehdä asioita, jotka voi mielekkäästi tehdä SQL:ssä | 5 |
| Käytetty `try`/`except` SQL-komennon ympärillä vain aiheellisesti | 5 |

Tarkempaa tietoa vaatimuksista on [teknisessä tarkastuslistassa](../lista).

### Sovelluksen turvallisuus (20 p)

| Salasanat tallennetaan tietokantaan asianmukaisesti | 1--5 |
| Käyttäjän oikeus nähdä sivun sisältö tarkastetaan | 1--5 |
| Käyttäjän oikeus lähettää lomake tarkastetaan | 1--5 |
| Käyttäjän syötteet tarkastetaan ennen tietokantaan lisäämistä | 1--5 |
| SQL-komennoissa käytetty parametreja | 1--5 |
| Sivut muodostetaan sivupohjien kautta | 1--5 |
| Lomakkeissa on estetty CSRF-aukko | 1--5 |

Tarkempaa tietoa vaatimuksista on [teknisessä tarkastuslistassa](../lista).

### Suuren tietomäärän käsittely (5 p)

| Sovellusta testattu suurella tietomäärällä ja raportoitu tulokset | 5 |
| Sovelluksessa käytössä tietokohteiden sivutus | 5 |
| Tietokantaan lisätty indeksi, joka nopeuttaa suuren tietomäärän käsittelyä | 5 |

Sopiva tapa raportoida tulokset on lisätä tiedosto `seed.py` repositorioon ja kirjoittaa tiedostoon `README.md` selostus sovelluksen toiminnasta suurella tietomäärällä.

### Vertaisarviointi ja palaute (5 p)

| Ensimmäinen vertaisarviointi annettu | 1--5 |
| Ensimmäinen vertaisarviointi tehty kattavasti | 4--5 |
| Toinen vertaisarviointi annettu | 1--5 |
| Toinen vertaisarviointi tehty kattavasti | 4--5 |
| Kurssipalaute annettu | 5 |

Kurssin vastuuhenkilö saa palautejärjestelmästä listan opiskelijoista, jotka ovat antaneet palautteen. Järjestelmästä ei näe, kuka on antanut tietyn palautteen.
