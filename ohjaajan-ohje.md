---
title: Ohjaajan ohje
permalink: /ohjaajan-ohje/
hide: true
---

# Ohjaajan ohje

Olennaista on antaa opiskelijoille _hyödyllistä_ palautetta, joka parantaa harjoitustyön laatua ja opettaa web-sovelluksen toteuttamiseen liittyviä asioita.

Välipalautuksissa deadline on sunnuntaina ja ohjaajan tulee antaa palaute seuraavan viikon keskiviikkoon mennessä, jotta opiskelijat saavat nopeasti palautteen, jonka avulla he pystyvät kehittämään työtä.

Välipalautuksen jälkeen merkitse Labtooliin pistemäärä, joka ilmaisee, miten hyvin välipalautuksen tavoitteet täyttyivät: 0 (ei ollenkaan), 1 (osittain), 2 (kokonaan). Välipalautusten pistemäärät eivät kuitenkaan vaikuta kurssin arviointiin.

## Välipalautus 1

* Tarkasta, että olet kurssin ohjaajana [Labtoolissa](https://study.cs.helsinki.fi/labtool/). Jos et ole, pyydä kurssin vastuuhenkilöä lisäämään sinut.
* Sovi muiden ohjaajien kanssa Slackissa töiden jakamisesta.
* Käy läpi sinulle kuuluvat työt. Tarkasta jokaisen työn kohdalla, että aihe on kurssille sopiva. Anna opiskelijalle lyhyt palaute Labtoolissa.
* Vinkkejä tämän välipalautuksen käsittelyyn:
  - Jos repositorion nimi on huono (ei kuvaa sovelluksen aihetta), neuvo opiskelijaa vaihtamaan nimi paremmaksi.
  - Jos sovelluksen aihe on sama kuin kurssin esimerkkisovelluksessa (huutokauppa tai keskustelualue), pyydä opiskelijaa valitsemaan jokin toinen aihe.

## Välipalautus 2

* Testaa opiskelijan sovellusta ja anna palautetta siitä.
* Tutustu sovelluksen koodiin ja anna palautetta siitä.
* Anna palautetta erityisesti seuraavista asioista:
  - Tekniset perusvaatimukset: toteuttaako opiskelija sovellusta oikealla tavalla?
  - Toimivuus ja käytettävyys: millainen kokemus sovelluksen käyttäjälle tulee?
  - Versionhallinta: onko repositoriossa oikeat tiedostot ja ovatko commit-viestit hyviä?
  - Ohjelmointityyli: onko koodi siistiä ja seuraako se Python-kielen käytäntöjä?
  - Tietokanta-asiat: onko SQL-skeema kunnossa ja käytetäänkö tietokantaa koodissa järkevästi?
* Jos sovelluksessa ei ole koodia, siitä ei tarvitse antaa palautetta.
* Vinkkejä tämän välipalautuksen käsittelyyn:
  - Varmista, että projektin rakenne on samanlainen kuin [esimerkkiprojektissa](https://github.com/pllk/huutokauppa), kuten että päätasolla on tiedostot `app.py`, `config.py`, `db.py` ja `schema.sql`.
  - Jos opiskelija tekee jotain selkeästi väärin (esim. teknisten vaatimusten vastaisesti), tämä on hyvä hetki tuoda asia esille.

## Välipalautus 3

* Testaa opiskelijan sovellusta ja anna palautetta siitä.
* Tutustu sovelluksen koodiin ja anna palautetta siitä.
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

## Lopullinen palautus

* Käy läpi [arvostelusivu](../arvostelu) ja kirjaa muistiin, mitkä kriteerit sovellus täyttää.
* Tarkasta, että opiskelija on tehnyt molemmat vertaisarvioinnit, ja pisteytä ne Labtoolissa (1 = arviointi tehty, 2 = kattava arviointi).
* Kurssin vastuuhenkilö pystyy luomaan listan, jossa on kurssipalautteen antaneiden opiskelijoiden opiskelijanumerot.
* Anna opiskelijalle palaute, jossa on tieto kunkin kriteerin täyttymisestä, lyhyt sanallinen yleispalaute sekä kurssin arvosana (tai tieto että ei hyväksytty).

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
