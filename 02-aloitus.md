---
title: Projektin aloitus
permalink: /aloitus/
hide: true
---

# Projektin aloitus

Kurssilla toteutetaan web-sovellus käyttäen Python-kieltä ja Flask-kirjastoa. Sovelluksen tiedot tallennetaan SQLite-tietokantaan.

Löydät sovelluksen toteuttamisen tueksi kurssimateriaalin tältä sivustolta. Lisäksi sinun kannattaa tutustua [esimerkkisovellukseen](../esimerkki) ja siihen liittyvään videosarjaan.

Kurssilla käytetään Git-versionhallintaa ja GitHub-palvelua. Jos et tunne näitä ennestään hyvin, sinun kannattaa tutustua myös [Git-ohjeisiin](../git).

## Aiheen valinta

Hyvä aihe sovellukselle on itseäsi kiinnostava aihe. Sovelluksen voi toteuttaa hyvin monenlaisista aiheista, kunhan perusvaatimukset täyttyvät.

Sovelluksen perusvaatimukset ovat:

* Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen.
* Käyttäjä pystyy lisäämään sovellukseen tietokohteita. Lisäksi käyttäjä pystyy muokkaamaan ja poistamaan lisäämiään tietokohteita.
* Käyttäjä näkee sovellukseen lisätyt tietokohteet. Käyttäjä näkee sekä itse lisäämänsä että muiden käyttäjien lisäämät tietokohteet.
* Käyttäjä pystyy etsimään tietokohteita hakusanalla tai muulla perusteella. Käyttäjä pystyy hakemaan sekä itse lisäämiään että muiden käyttäjien lisäämiä tietokohteita.
* Sovelluksessa on käyttäjäsivut, jotka näyttävät jokaisesta käyttäjästä tilastoja ja käyttäjän lisäämät tietokohteet.
* Käyttäjä pystyy valitsemaan tietokohteelle yhden tai useamman luokittelun. Mahdolliset luokat ovat tietokannassa.
* Sovelluksessa on pääasiallisen tietokohteen lisäksi toissijainen tietokohde, joka täydentää pääasiallista tietokohdetta. Käyttäjä pystyy lisäämään toissijaisia tietokohteita omiin ja muiden käyttäjien tietokohteisiin liittyen.

Esimerkkisovellus sekä tämän sivun lopussa olevat esimerkkiaiheet selventävät, mitä perusvaatimukset tarkoittavat käytännössä.

Sovelluksen aiheesta riippuu, mitä tietokohteet ovat käytännössä. Esimerkkisovelluksessa pääasiallinen tietokohde on tavaran myynti-ilmoitus ja toissijainen tietokohde on ilmoituksessa oleva huuto.

Voit halutessasi toteuttaa perusvaatimusten lisäksi sovellukseen muitakin ominaisuuksia.

## Tekniset vaatimukset

Tekniset perusvaatimukset ovat:

* Sovellus on toteutettu samaan tapaan kuin kurssimateriaalin esimerkeissä.
* Sovellus on toteutettu Python-kielellä ja Flask-kirjastoa käyttäen.
* Sovellus käyttää SQLite-tietokantaa.
* Kehitystyössä on käytetty Git-versionhallintaa ja GitHub-palvelua.
* Sovelluksen käyttöliittymä muodostuu HTML-sivuista.
* Sovelluksessa ei ole käytetty JavaScript-koodia.
* Tietokantaa käytetään suoraan SQL-komennoilla (ei ORMin kautta).
* Sovellus ei käytä kirjaston `flask` lisäksi muita erikseen asennettavia kirjastoja.

## Esimerkkiaiheita

### Ruokareseptit

* Sovelluksessa käyttäjät pystyvät jakamaan ruokareseptejään. Reseptissä lukee tarvittavat ainekset ja valmistusohje.
* Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen.
* Käyttäjä pystyy lisäämään reseptejä ja muokkaamaan ja poistamaan niitä.
* Käyttäjä näkee sovellukseen lisätyt reseptit.
* Käyttäjä pystyy etsimään reseptejä hakusanalla.
* Käyttäjäsivu näyttää, montako reseptiä käyttäjä on lisännyt ja listan käyttäjän lisäämistä resepteistä.
* Käyttäjä pystyy valitsemaan reseptille yhden tai useamman luokittelun (esim. alkuruoka, intialainen, vegaaninen).
* Käyttäjä pystyy antamaan reseptille kommentin ja arvosanan. Reseptistä näytetään kommentit ja keskimääräinen arvosana.

Tässä pääasiallinen tietokohde on ruokaresepti ja toissijainen tietokohde on kommentti reseptiin.

### Sulkapalloseura

* Sovelluksessa käyttäjät pystyvät etsimään peliseuraa sulkapalloon. Ilmoituksessa lukee missä ja milloin pelivuoro on sekä tarvittava pelaajien määrä.
* Käyttäjä pystyy luomaan tunnuksen ja kirjautumaan sisään sovellukseen.
* Käyttäjä pystyy lisäämään ilmoituksia ja muokkaamaan ja poistamaan niitä.
* Käyttäjä näkee sovellukseen lisätyt ilmoitukset.
* Käyttäjä pystyy etsimään ilmoituksia sen perusteella, milloin vuoro on.
* Käyttäjäsivu näyttää, montako ilmoitusta käyttäjä on lähettänyt ja listan ilmoituksista.
* Käyttäjä pystyy valitsemaan ilmoitukselle yhden tai useamman luokittelun (esim. Kumpula Unisport, keskitason pelaaja).
* Käyttäjä pystyy ilmoittautumaan pelivuoroon. Ilmoituksessa näytetään, ketkä käyttäjät ovat ilmoittautuneet.

Tässä pääasiallinen tietokohde on ilmoitus ja toissijainen tietokohde on ilmoittautuminen.
