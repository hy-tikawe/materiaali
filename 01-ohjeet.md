---
title: Ohjeet ja aikataulu
permalink: /ohjeet/
---

# Ohjeet ja aikataulu

Kevään 2025 periodin 3 ryhmän aikataulu on seuraava:

| ti 14.1.2025 | Aloitusluento klo 16–18 (Exactum D122) |
| su 19.1.2025 | Välipalautus 1 |
| su 2.2.2025 | Välipalautus 2 |
| pe 7.2.2025 | Vertaisarvioinnin deadline |
| su 16.2.2025 | Välipalautus 3 |
| pe 21.2.2025 | Vertaisarvioinnin deadline |
| su 2.3.2025 | Lopullinen palautus |

Voit keskustella kurssiin liittyvistä asioista kurssin [Discord-ryhmässä](https://study.cs.helsinki.fi/discord/join/tikawe), jossa on paikalla kurssin ohjaajia ja opiskelijoita.

Lisäksi ohjausta on tarjolla Kumpulan kampuksella Exactumin salissa BK107 tiistaisin klo 14–18, keskiviikkoisin klo 12–15 sekä torstaisin klo 10–13.

## Kurssin yleiskuva

Kurssilla toteutetaan tietokantaa käyttävä web-sovellus. Kurssilla käytetään Python-kieltä, Flask-kirjastoa ja SQLite-tietokantaa sovelluksen toteuttamiseen.

[Aloitussivu](../aloitus) antaa ohjeet aiheen valintaan ja kuvaa sovellukseen liittyvät perusvaatimukset. Sivulla on joitakin sovelluksen esimerkkiaiheita.

[Esimerkkisovellus](../esimerkki) on malli siitä, millainen lopullisen sovelluksen tulisi olla. Esimerkkisovellukseen liittyy videosarja, joka näyttää sovelluksen luontiprosessin.

[Arvostelusivu](../arvostelu) kuvaa tarkemmin kurssin vaatimukset ja arvostelutavan.

Kurssilla on sallittua käyttää vapaasti nettilähteitä ja tekoälyä kurssin suorittamisen tukena. Huomaa kuitenkin, että sovelluksen tulee olla kurssin vaatimusten mukainen ja saman tyylinen kuin kurssimateriaalissa.

## Kurssin eteneminen

Kurssiin kuuluu kolme välipalautusta ja lopullinen palautus. Kaikkien palautusten deadline on klo 23:59 sunnuntaina.

### Välipalautus 1

* Luo GitHubiin julkinen repositorio harjoitustyötä varten. Nimeä repositoriosi kuvaavasti.
* Valitse projektille aihe ja kirjoita `README.md`-tiedostoon kuvaus, joka esittelee sovelluksen keskeiset toiminnot. Kirjoita kuvaus samassa muodossa kuin aloitussivun esimerkkiaiheissa ja esimerkkisovelluksessa.
* Kirjaudu [Labtooliin](https://study.cs.helsinki.fi/labtool/courses/TKT20019.2025.K.K.2) ja ilmoita siellä projektisi GitHub-osoite.
* Saat seuraavan viikon alussa ohjaajalta palautteen aiheesta Labtooliin.

### Välipalautus 2

* Tavoitteena on, että sovelluksessa on ainakin seuraavat toiminnot:
  - Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen.
  - Käyttäjä pystyy lisäämään, muokkaamaan ja poistamaan tietokohteita.
  - Käyttäjä näkee sovellukseen lisätyt tietokohteet.
  - Käyttäjä pystyy etsimään tietokohteita hakusanalla tai muulla perusteella.
* `README.md`-tiedoston tulee kuvata, mikä on sovelluksen nykyinen tilanne.
* Saat seuraavan viikon alussa ohjaajalta palautteen sovelluksesta Labtooliin.

### Välipalautus 3

* Tavoitteena on, että sovelluksessa on ainakin seuraavat toiminnot:
  - Sovelluksessa on käyttäjäsivut, jotka näyttävät tilastoja ja käyttäjän lisäämät tietokohteet.
  - Käyttäjä pystyy valitsemaan tietokohteelle yhden tai useamman luokittelun. Mahdolliset luokat ovat tietokannassa.
  - Käyttäjä pystyy lähettämään toisen käyttäjän tietokohteeseen liittyen jotain lisätietoa, joka tulee näkyviin sovelluksessa.
* `README.md`-tiedoston tulee kuvata, mikä on sovelluksen nykyinen tilanne.
* Saat seuraavan viikon alussa ohjaajalta palautteen sovelluksesta Labtooliin.

### Vertaisarviointi

Kurssiin kuuluu kaksi [vertaisarviointia](../vertaisarviointi), joissa annetaan palautetta toisen opiskelijan työstä. Saat ohjeet vertaisarviointiin sähköpostitse välipalautusten 2 ja 3 jälkeen.

### Lopullinen palautus

* Kurssi arvostellaan tämän sovelluksen version perusteella.
* `README.md`-tiedoston tulee kuvata, millainen lopullinen sovellus.
* Ohjaaja arvostelee työn ja antaa palautetta Labtooliin. Ohjaaja arvostelee työn kuukauden kuluessa deadlinesta.
* Anna lisäksi [kurssipalaute](https://norppa.helsinki.fi/targets/84703809) viimeistään seuraavana päivänä lopullisen palautuksen deadlinen jälkeen.

## Ohjeita

* Ennen sovelluksen toteuttamisen aloittamista sinun kannattaa tutustua kurssimateriaaliin ja tehdä pieniä kokeiluja, jotta saat harjoiteltua kurssilla käytettyjä tekniikoita.
* Neuvoja tietokannan suunnitteluun löydät kurssin _Tietokantojen perusteet_ materiaalista. Erityisesti kurssin materiaalin [luku 6](https://tikape.mooc.fi/kevat-2025/osa6/) on hyödyllinen.
* Sovellus ja tietokanta rakentuvat pikkuhiljaa ja niihin tulee muutoksia. Kannattaa aloittaa yksinkertaisesta ja muuttaa rakennetta tarvittaessa myöhemmin.
* Palautuksissa ohjaaja tutustuu projektisi uusimpaan versioon GitHubissa. Pidä huoli siitä, että sovelluksen ajantasainen versio on saatavilla näissä paikoissa.
* Sovelluksen dokumentaatio luodaan tiedostoon `README.md`, joka näkyy GitHubissa projektin etusivulla. Kirjoita dokumentaatio sellaista henkilöä varten, joka haluaa saada käsityksen sovelluksesta ja mahdollisesti ottaa sen käyttöön itse tai kehittää sovellusta.
* Oleellinen asia kurssilla on sovelluksen toimivuus: millainen käyttökokemus tulee testaajalle, joka käyttää sovellusta. Jos sovellus ei toimi, muut osa-alueet eivät voi pelastaa sitä.
* Jos jokin asia kurssilla on epäselvä, niin otathan yhteyttä ohjaajaan tai kurssin [vastuuhenkilöön](mailto:ahslaaks@cs.helsinki.fi).
