---
title: Ohjaajan ohje
permalink: /ohjaajan-ohje/
hide: true
---

# Ohjaajan ohje

Olennaista on antaa opiskelijoille _hyödyllistä_ palautetta, joka parantaa harjoitustyön laatua ja opettaa web-sovelluksen toteuttamiseen liittyviä asioita.

Palautteessa on hyvä olla kannustava, mutta kuitenkin keskittyä antamaan tietoa parannettavista asioista.

Välipalautuksissa deadline on sunnuntaina ja ohjaajan tulee antaa palaute seuraavan viikon keskiviikkoon mennessä, jotta opiskelijat saavat nopeasti palautteen, jonka avulla he pystyvät kehittämään työtä.

Välipalautuksen jälkeen merkitse Labtooliin pistemäärä, joka ilmaisee, miten hyvin välipalautuksen tavoitteet täyttyivät: 0 (ei ollenkaan), 1 (osittain), 2 (kokonaan). Välipalautusten pistemäärät eivät kuitenkaan vaikuta kurssin arviointiin.

Labtoolissa on jokaiselle välipalautukselle ja loppupalautukselle checklist tarkastuksen avuksi. Checklist on tehty helpottamaan arviointityötä, mutta anna sen lisäksi opiskelijalle tarvittaessa muutakin palautetta. Voit halutessasi kopioida osaksi annettavaa palautetta checklistin automaattisesti tuottamaa palautetekstiä. Huomaa kuitenkin, että automaattinen palauteteksti tarvitsee usein muokkausta eikä se ole vaatimusten kannalta kattavaa.

## Välipalautus 1

* Tarkasta, että olet kurssin ohjaajana [Labtoolissa](https://study.cs.helsinki.fi/labtool/). Jos et ole, pyydä kurssin vastuuhenkilöä lisäämään sinut.
* Sovi muiden ohjaajien kanssa Slackissa töiden jakamisesta.
* Käy läpi sinulle kuuluvat työt. Tarkasta jokaisen työn kohdalla, että aihe on kurssille sopiva. Anna opiskelijalle lyhyt palaute Labtoolissa.
* Vinkkejä tämän välipalautuksen käsittelyyn:
  - Jos repositorion nimi on huono (ei kuvaa sovelluksen aihetta), neuvo opiskelijaa vaihtamaan nimi paremmaksi.
  - Jos sovelluksen aihe on sama kuin kurssin esimerkkisovelluksessa (huutokauppa tai keskustelualue), pyydä opiskelijaa valitsemaan jokin toinen aihe.
  - Jos työ on jatkoa aiemmalta kurssilta, voit halutessasi huomauttaa ilmeisistä ongelmista, mutta tässä välipalautuksessa ei ole vielä tarkoitus testata sovellusta tai perehtyä koodiin.


## Välipalautus 2

* Testaa opiskelijan sovellusta.
* Tutustu sovelluksen koodiin.
* Anna edellisten kohtien perusteella sovelluksesta palautetta.
  - Harjoitustyöhön tutustuessa kannattaa puutteita kirjata checklist-merkintöjen lisäksi väliaikaisesti erilliseen tekstieditoriin tai labtoolin "review notes" -kohtaan, jolloin palautteen kirjoittaminen on helpompaa eivätkä mahdolliset ongelmat unohdu.
* Anna palautetta erityisesti seuraavista asioista:
  - Tekniset perusvaatimukset: toteuttaako opiskelija sovellusta oikealla tavalla?
  - Toimivuus ja käytettävyys: millainen kokemus sovelluksen käyttäjälle tulee?
  - Versionhallinta: onko repositoriossa oikeat tiedostot ja onko commitit tehty hyvin?
    - Kiinnitä huomiota commit-viestien kuvaavuuteen sekä siihen, ovatko commitit yhtenäisiä ja selkeästi rajattuja kokonaisuuksia.
  - Ohjelmointityyli: onko koodi siistiä ja seuraako se Python-kielen käytäntöjä?
  - Tietokanta-asiat: onko SQL-skeema kunnossa ja käytetäänkö tietokantaa koodissa järkevästi?
* Jos sovelluksessa ei ole koodia, siitä ei tarvitse antaa palautetta.
* Vinkkejä tämän välipalautuksen käsittelyyn:
  - Varmista, että projektin rakenne on samanlainen kuin [esimerkkiprojektissa](https://github.com/pllk/huutokauppa), kuten että päätasolla on tiedostot `app.py`, `config.py`, `db.py` ja `schema.sql`.
  - Jos opiskelija tekee jotain selkeästi väärin (esim. teknisten vaatimusten vastaisesti), tämä on hyvä hetki tuoda asia esille.

## Välipalautus 3

* Valitse opiskelijan sovelluksesta jokin keskeinen toiminto (kuten uuden tietokohteen lisäys) ja tarkasta, että:
  - Sovellus varmistaa, että käyttäjällä on oikeus nähdä sivu ja suorittaa toiminto.
  - Sovelluksessa on jotain tiedon validointia (esim. maksimipituus tietokantaan lisättävälle tiedolle).
* Anna tarvittaessa palautetta oikeuksien tarkastamisen tai validoinnin puuttumisesta.
* Tarkasta vertaispalautteet ja anna opiskelijalle palautetta siitä, oliko annettu vertaispalaute suppea vai kattava ja miten parantaa vertaispalautetta. Tämän ensimmäisen vertaisarvion palautteen on tarkoitus ohjeistaa opiskelijaa kattavan vertaispalautteen vaatimusten täyttämiseen, mutta olla pisteytyksessä salliva (eli vaatimustaso 2p voi olla hieman matalampi).
  - Jos vertaisarvio on mielestäsi suppea, mutta opiskelija on selkeästi hieman yrittänyt parempaa, niin anna 2p, mutta kuitenkin varoita opiskelijaa, että vastaava vertaisarvio ei riitä 2p vaatimuksiin jälkimmäisessä vertaisarviossa.
  - Oliko palautteessa kuvattu mitä oli testattu?
  - Onko palaute rakenteeltaan selkeä?
  - Löysikö opiskelija sovellusta kokeillessaan jonkun ongelman/toimintavirheen? Etsikö opiskelija kyseisen ongelman aiheuttajan koodista ja kertoi missä se on? (Erityisen kiitettävää olisi konkreettinen korjausehdotus)
  - Oliko vertaisarvio riittävän kattava, vai jäikö se vain muutamaksi kommentiksi?
* "Ongelmattomien" töiden vertaisarviointi:
  - Näissäkin olisi hyvä edes kertoa, mitä on testattu.
  - [Kattavan vertaisarvion esimerkissä](https://github.com/pllk/huutokauppa/issues/3) on mainittu monia laatutekijöitä, joista ainakin muutama (tai jotain vastaavaa) on usein relevantti millä tahansa harjoitustyöllä.
* Jos vertaisarvio on tehty, mutta siinä ei selkeästi ole edes yritetty kattavaa arviointia, anna 1p.

## Välipalautus 4

* Testaa opiskelijan sovellusta.
* Tutustu sovelluksen koodiin.
* Anna edellisten kohtien perusteella palautetta sovelluksesta.
* Anna palautetta erityisesti seuraavista asioista:
  - Toimivuus ja käytettävyys: mitä kannattaa parantaa vielä ennen lopullista palautusta?
  - Sovelluksen turvallisuus: tarkastaako sovellus, että käyttäjällä on oikeus nähdä sivu ja lähettää lomake?
  - Sovelluksen turvallisuus: onko sovelluksessa SQL-injektiota, XSS-aukkoa tai CSRF-aukkoa?
  - Ohjelmointityyli: onko koodi jaettu järkevästi osiin moduuleiksi ja funktioiksi?
  - Tietokanta-asiat: tehdäänkö koodissa tiedon käsittelyä, jota kuuluisi tehdä SQL:ssä?
* Jos sovellus ei ole muuttunut viime kerrasta, siitä ei tarvitse antaa palautetta.
* Vinkkejä tämän välipalautuksen käsittelyyn:
  - Tavallinen puute sovelluksissa on, että CSRF-aukkoa ei ole estetty. Tämä on hyvä hetki tuoda asia esille.
  - Varmista, ettei sovellus käytä Flask-kirjaston lisäksi muita Python-kirjastoja.
  - Varmista, ettei sovellus käytä JavaScriptia eikä ulkoasukirjastoja (kuten Bootstrap, Tailwind, Font Awesome).
  - Muutenkin jos sovelluksessa on vielä puutteita, jotka estäisivät kurssin läpipääsyn, tuo tämä selkeästi esille.

## Välipalautus 5

* Testaa sovellusta ja lue koodia.
* Labtoolin checklistissä on kaikki loppuarvostelun perusvaatimukset: käy ne läpi, ja anna palautetta opiskelijalle siitä, mikä on työn tämänhetkinen tilanne kurssin läpipääsyn kannalta, ja miten tarvittaessa korjata tilanne.
* Tarkasta vertaispalautteet ja anna opiskelijalle palautetta siitä, oliko annettu vertaispalaute suppea vai kattava ja perustelut tälle.
  - Vertaa esimerkkiarvioihin: jos vertaisarvio vastaa selkeästi [suppeaa esimerkkiä](https://github.com/pllk/huutokauppa/issues/2), se saa 1p. Jos se taas mielestäsi vastaa tai on riittävän lähellä [kattavaa esimerkkiä](https://github.com/pllk/huutokauppa/issues/3), se saa 2p.

## Lopullinen palautus

* Tavoitteena on, että arvostelut olisivat valmiina 2 viikon sisään lopullisesta palautusmääräajasta. Jos tämä on aikataulusi kannalta ongelmallisen lyhyt aika, ota yhteys Anttiin.
* Käy läpi [arvostelusivu](../arvostelu) ja kirjaa muistiin, mitkä kriteerit sovellus täyttää.
* Kurssin vastuuhenkilö pystyy luomaan listan, jossa on kurssipalautteen antaneiden opiskelijoiden opiskelijanumerot.
* Anna opiskelijalle palaute, jossa on:
  - kurssin arvosana (tai tieto että ei hyväksytty)
  - lyhyt sanallinen yleispalaute
  - mainittu, missä määrin kriteerit täyttyivät (esim: "Kaikki arvosanan 3 perusvaatimukset täyttyivät.")
  - erittely kriteereistä, jotka jäivät täyttymättä (esim: "Kaikki muuttujat ja funktiot on nimetty yhdellä kirjaimella, mikä tekee koodin ymmärtämisestä vaikeaa. ... (jne. muut puutteet)")
* Palautteessa voi olla hyvä ryhmitellä kunkin arvosanan kriteerit erillisiksi ryhmiksi, jota opiskelijalle ei tule epäselvyyttä, mitkä kriteerit liittyvät mihin arvosanaan.
* Yksittäisestä pienimuotoisesta puutteesta ei ehkä kannata heti pudottaa arvosanaa. Jos on epävarmuutta mikä on pienimuotoista, kannattaa kysyä Slackissa tapauskohtaisesti.
* Merkittävistä arvosteluun vaikuttamattomista puutteista tai parannusehdotuksista voi myös mainita, mutta tällöin tulee tuoda selkeästi ilmi, että nämä eivät vaikuttaneet arvosteluun.

Pylint ja grep ovat käteviä työkaluja sovelluksen arvioinnissa. Esimerkiksi seuraava komento etsii Python-tiedostoista liian pitkiä rivejä:

```console
$ pylint *.py | grep line-too-long
```

Tämän kurssin arvioinnin kannalta keskeisiä ovat:

* `bad-indentation`: väärä sisennys
* `line-too-long`: liian pitkä rivi
* `invalid-name`: väärin nimetty muuttuja/funktio
* `bad-whitespace`: virhe välien käytössä
* `superfluous-parens`: ylimääräiset sulkeet

Komento grep on muutenkin hyödyllinen. Esimerkiksi seuraava komento etsii HTML-tiedostoista kohtia, jotka viittaavat JavaScriptin käyttämiseen:

```console
$ grep script *.html
```
