---
title: Ohjeet ja aikataulu
permalink: /ohjeet/
---

# Ohjeet ja aikataulu

Kevään 2026 periodin 3 aikataulu on seuraava:

| ti 13.1.2026 | Aloitusluento klo 16–18 (Exactum D122) |
| su 18.1.2026 | Välipalautus 1 |
| su 1.2.2026 | Välipalautus 2 |
| su 8.2.2026 | Vertaisarvioinnin deadline |
| su 15.2.2026 | Välipalautus 3 |
| su 22.2.2026 | Vertaisarvioinnin deadline |
| su 1.3.2026 | Lopullinen palautus |

Voit keskustella kurssiin liittyvistä asioista kurssin [Discord-ryhmässä](https://study.cs.helsinki.fi/discord/join/tikawe), jossa on paikalla kurssin ohjaajia ja opiskelijoita. Lisäksi järjestetään pajaohjausta Exactumin salissa BK107 keskiviikkoisin klo 12–16 sekä perjantaisin klo 12–16.

## Tärkeät deadlinet

- Välipalautuksen 1 deadlineen mennessä sinun tulee kirjautua Labtooliin ja ilmoittaa siellä linkki sovelluksesi GitHub-repositorioon.
- Välipalautuksen 2 deadlineen mennessä repositoriossasi tulee olla koodia, jossa on toteutettu joitakin sovelluksen ominaisuuksia.
- Vertaisarvioinnit ovat pakollisia, ja sinun tulee tehdä kumpikin arviointi deadlineen mennessä.
- Sovelluksen tulee olla valmis lopullisen palautuksen deadlineen mennessä.

## Kurssin yleiskuva

Kurssilla toteutetaan tietokantaa käyttävä web-sovellus. Kurssilla käytetään Python-kieltä, Flask-kirjastoa ja SQLite-tietokantaa sovelluksen toteuttamiseen.

[Aloitussivu](../aloitus) antaa ohjeet aiheen valintaan ja kuvaa sovellukseen liittyvät perusvaatimukset. Sivulla on joitakin sovelluksen esimerkkiaiheita.

[Esimerkkisovellus](../esimerkki) on malli siitä, millainen lopullisen sovelluksen tulisi olla. Esimerkkisovellukseen liittyy videosarja, joka näyttää sovelluksen luontiprosessin.

[Arvostelusivu](../arvostelu) kuvaa tarkemmin kurssin vaatimukset ja arvostelutavan.

Kurssilla on sallittua käyttää vapaasti tekoälyä [CurreChatin](https://curre.helsinki.fi/chat) (yliopiston ChatGPT-käyttöliittymä) kautta, myös koodin tuottamiseen. Huomaa kuitenkin, että sovelluksen tulee olla kurssin vaatimusten mukainen ja saman tyylinen kuin kurssimateriaalissa. Muut tavat käyttää tekoälyä eivät ole sallittuja kurssilla.

## Kurssin eteneminen

Kurssiin kuuluu kolme välipalautusta ja lopullinen palautus. Kaikkien palautusten deadline on klo 23:59 sunnuntaina.

Välipalautuksen ja palautuksen tekemiseen riittää, että repositoriosi on ajan tasalla. Sinun ei tarvitse tehdä mitään erityistä Labtoolissa palautusta varten.

### Välipalautus 1

* Luo GitHubiin julkinen repositorio harjoitustyötä varten. Nimeä repositoriosi kuvaavasti.
* Valitse projektille aihe ja kirjoita `README.md`-tiedostoon kuvaus, joka esittelee sovelluksen keskeiset toiminnot. Kirjoita kuvaus samassa muodossa kuin aloitussivun esimerkkiaiheissa ja esimerkkisovelluksessa.
* Kirjaudu [Labtooliin](https://study.cs.helsinki.fi/labtool/courses/TKT20019.2026.K.K.1) ja ilmoita siellä projektisi GitHub-osoite.
* Saat seuraavan viikon alussa ohjaajalta palautteen aiheesta Labtooliin.
* Vinkkejä palautukseen:
  - Valitse repositorion nimi niin, että se kuvaa hyvin sovellustasi. Esimerkiksi jos teet reseptisovelluksen, voit valita esimerkiksi nimen `reseptit`.

### Välipalautus 2

* Tavoitteena on, että sovelluksessa on ainakin seuraavat toiminnot:
  - Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen.
  - Käyttäjä pystyy lisäämään, muokkaamaan ja poistamaan tietokohteita.
  - Käyttäjä näkee sovellukseen lisätyt tietokohteet.
  - Käyttäjä pystyy etsimään tietokohteita hakusanalla tai muulla perusteella.
* `README.md`-tiedoston tulee kuvata, millainen sovellus on ja miten sitä voi testata.
* Saat seuraavan viikon alussa ohjaajalta palautteen sovelluksesta Labtooliin.
* Vinkkejä palautukseen:
  - Muista antaa `README.md`-tiedostossa ohjeet siihen, miten sovelluksen testaaja saa käynnistettyä sovelluksen omalla koneellaan.
  - Tiedosto `database.db` ei kuulu repositorioon. Sovelluksen testaajan pitäisi pystyä luomaan tietokanta `.sql`-tiedostojen perusteella.

### Välipalautus 3

* Tavoitteena on, että sovelluksessa on ainakin seuraavat toiminnot:
  - Sovelluksessa on käyttäjäsivut, jotka näyttävät tilastoja ja käyttäjän lisäämät tietokohteet.
  - Käyttäjä pystyy valitsemaan tietokohteelle yhden tai useamman luokittelun. Mahdolliset luokat ovat tietokannassa.
  - Käyttäjä pystyy lähettämään toisen käyttäjän tietokohteeseen liittyen jotain lisätietoa, joka tulee näkyviin sovelluksessa.
* `README.md`-tiedoston tulee kuvata, millainen sovellus on ja miten sitä voi testata.
* Saat seuraavan viikon alussa ohjaajalta palautteen sovelluksesta Labtooliin.
* Vinkkejä palautukseen:
  - Muista estää sovelluksessasi CSRF-aukko kurssimateriaalin mukaisesti.
  - Pylint on hyödyllinen työkalu, jonka avulla voit saada ehdotuksia koodisi parantamiseksi.

### Vertaisarviointi

Kurssiin kuuluu kaksi [vertaisarviointia](../vertaisarviointi), joissa annetaan palautetta toisen opiskelijan työstä. Saat ohjeet vertaisarviointiin sähköpostitse välipalautusten 2 ja 3 jälkeen.

### Lopullinen palautus

* Kurssi arvostellaan tämän sovelluksen version perusteella.
* `README.md`-tiedoston tulee kuvata, millainen sovellus on ja miten sitä voi testata.
* Ohjaaja arvostelee työn ja antaa palautetta Labtooliin. Ohjaaja arvostelee työn kuukauden kuluessa deadlinesta.

### Kurssipalaute

Anna [kurssipalaute](https://norppa.helsinki.fi/targets/95022637) viimeistään seuraavana päivänä lopullisen palautuksen deadlinen jälkeen. Palaute on anonyymia ja vaikuttaa kurssin kehitykseen.

Kurssipalaute ja vastuuhenkilön kommentit kootaan [palauteyhteenvetoon](../palaute).

## Ohjeita

* Ennen sovelluksen toteuttamisen aloittamista sinun kannattaa tutustua kurssimateriaaliin ja tehdä pieniä kokeiluja, jotta saat harjoiteltua kurssilla käytettyjä tekniikoita.
* Neuvoja tietokannan suunnitteluun löydät kurssin _Tietokantojen perusteet_ materiaalista. Erityisesti kurssin materiaalin [luku 6](https://tikape.mooc.fi/kevat-2026/osa6/) on hyödyllinen.
* Sovellus ja tietokanta rakentuvat pikkuhiljaa ja niihin tulee muutoksia. Kannattaa aloittaa yksinkertaisesta ja muuttaa rakennetta tarvittaessa myöhemmin.
* Palautuksissa ohjaaja tutustuu projektisi uusimpaan versioon GitHubissa. Pidä huoli siitä, että GitHubissa on sovelluksesi ajantasainen versio.
* Sovelluksen dokumentaatio luodaan tiedostoon `README.md`, joka näkyy GitHubissa projektin etusivulla. Kirjoita dokumentaatio sellaista henkilöä varten, joka haluaa saada käsityksen sovelluksesta ja mahdollisesti ottaa sen käyttöön itse tai kehittää sovellusta.
* Oleellinen asia kurssilla on sovelluksen toimivuus: millainen käyttökokemus tulee testaajalle, joka käyttää sovellusta. Jos sovellus ei toimi, muut osa-alueet eivät voi pelastaa sitä.
* Jos jokin asia kurssilla on epäselvä, niin otathan yhteyttä ohjaajaan tai kurssin [vastuuhenkilöön](mailto:ahslaaks@cs.helsinki.fi).
