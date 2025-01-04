---
title: Gitin käyttäminen
permalink: /git/
hide: true
---

# Gitin käyttäminen

TODO

## Projektin aloitus

Tehdään GitHubiin uusi repositorio nimellä `tikawe-test`. Valitaan, että repositorio on julkinen (public) ja siinä on valmiina README-tiedosto (add README file).

Repositoriossa on valmiina tiedosto `README.md`, jonka sisällön pitäisi olla seuraava:

```
# tikawe-test
```

Muutetaan tiedostoa GitHubissa seuraavasti:

```
# Testiprojekti

Tämä on esimerkki repositorion luomisesta.
```

Katsotaan seuraavaksi, miten voimme käsitellä repositoriota omalla koneellamme. Kun repositorio on luotu GitHubiin, voimme kloonata eli tehdä repositoriosta kopion omalle koneelleemme seuraavasti:

```console
$ git clone git@github.com:[tunnus]/tikawe-test.git
Cloning into 'tikawe-test'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
```

Tässä komento `git clone` luo hakemiston `tikawe-test` ja kloonaa siihen saman nimisen repositorion sisällön GitHubista. Komennossa kohdassa `[tunnus]` tulee olla GitHub-tunnus, jolle repositorio on luotu.

Repositorion kloonaamisen jälkeen voimme siirtyä hakemistoon `tikawe-test` ja tarkastaa, että hakemiston sisältö näyttää oikealta:

```console
$ cd tikawe-test
$ ls
README.md
$ cat README.md
# Testiprojekti

Tämä on esimerkki repositorion luomisesta.
```

Tilanne näyttää hyvältä, koska hakemistossa on tiedosto `README.md`, jonka sisältö on oikea. Katsotaan vielä repositorion muokkaushistoria komennolla `git log`:

```console
$ git log
commit f1fb51cbbd60f3227d6d02bcd73ab98617d28a39 (HEAD -> main, origin/main, origin/HEAD)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Sat Jan 4 16:37:05 2025 +0200

    Update README.md

commit c8b5097693799c4e542d71cd1cc4acbba7d65a68
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Sat Jan 4 16:32:30 2025 +0200

    Initial commit
```

Tässä näkyy, että repositorioon on tehty kaksi commitia: aloituscommit sekä aiemmin GitHubissa tekemämme tiedoston `README.md` muokkaus.

Voimme nyt kehittää sovellusta hakemistossa `tikawe-test` ja tallentaa muutokset versionhallintaan. Tehdään kokeeksi hakemistoon yksinkertainen esimerkkisovellus samaan tapaan kuin kurssimateriaalin alussa. Seuraavat komennot ottavat käyttöön virtuaaliympäristön ja asentavat Flask-kirjaston:

```console
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install flask
```

Lisätään hakemistoon tiedosto `app.py`, jonka sisältö on seuraava:

{: .code-title }
app.py
```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return "Heipparallaa!"
```

Kokeillaan vielä, että sovellus toimii:

```console
$ flask run
```

Sovellus näyttää toimivan, joten voimme tehdä commitin eli tallentaa tekemämme muutokset versionhallintaan. Tarkastetaan ensin komennolla `git status`, mitä on muuttunut:

```console
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	__pycache__/
	app.py
	venv/

nothing added to commit but untracked files present (use "git add" to track)
```

Komento näyttää, että hakemistossa on tiedosto `app.py` sekä kaksi alihakemistoa `__pycache__` ja `venv`, jotka eivät ole repositoriossa. Tiedoston `app.py` loimme itse ja alihakemistot syntyivät automaattisesti virtuaaliympäristön luomisen ja sovelluksen suorittamisen yhteydessä.

Hyvä periaate on säilyttää repositoriossa sovelluksen koodia mutta ei oman koneen ympäristöön liittyviä tiedostoja. Tässä tapauksessa haluamme lisätä tiedoston `app.py` repositorioon mutta emme alihakemistoja.

Komento `git add` lisää tiedoston ehdolle lisättäväksi repositorioon seuraavassa commitissa. Voimme käyttää komentoa näin:

```console
$ git add app.py
```

Tämän jälkeen on taas hyvä tarkastaa hakemiston tilanne:

```console
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   app.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	__pycache__/
	venv/
```

Tilanne näyttää hyvältä, koska tiedosto `app.py` on menossa repositorioon ja alihakemistot eivät ole menossa. Suoritetaan seuraavaksi komento `git commit`, joka tekee muutoksen paikalliseen repositorioon:

```console
$ git commit -m "Add application"
[main d39396c] Add application
 1 file changed, 7 insertions(+)
 create mode 100644 app.py
```

Tässä `Add application` on commit-viesti, joka ilmaisee, millä tavalla kyseinen commit muuttaa repositoriota.

Nyt muutos on tehty oman koneemme repositorioon mutta ei vielä GitHubin repositorioon. Suoritetaan vielä komento `git push`, joka kopioi paikallisen repositorion sisällön GitHubiin:

```console
(venv) $ git push
```

Tämän komennon suorittamisen jälkeen repositorioon lisätty tiedosto `app.py` näkyy myös GitHubissa.

Tarkastetaan vielä lopuksi repositorion muutoshistoria:

```console
$ git log
commit d39396c7fd791c60bc30adcd66cd54a3a44a7112 (HEAD -> main, origin/main, origin/HEAD)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Sat Jan 4 17:13:20 2025 +0200

    Add application

commit f1fb51cbbd60f3227d6d02bcd73ab98617d28a39
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Sat Jan 4 16:37:05 2025 +0200

    Update README.md

commit c8b5097693799c4e542d71cd1cc4acbba7d65a68
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Sat Jan 4 16:32:30 2025 +0200

    Initial commit
```

Tilanne näyttää hyvältä, koska äsken tekemämme commit on ilmestynyt listaan aiempien commitien perään.

## Miten tehdä hyvä commit?

Commitin tekijän on päätettävä kaksi asiaa: mitä tiedostoja commitiin tulee mukaan ja mikä on commitin viesti. Huonoin ratkaisu on laittaa mukaan sokkona kaikki muutetut tiedostot ja viestiksi "Some changes" tai vastaavaa.

Commitissa tulisi olla muutoksia, jotka todella halutaan kaikkien näkyville repositorioon ja jotka liittyvät tiettyyn yksittäiseen asiaan (kuten uuden ominaisuuden toteutus tai jonkin bugin korjaus). Tämän vuoksi on hyvä katsoa komennolla `git status`, mitä on tapahtunut, ja valita commitiin oikeat tiedostot. Jos muokkaat samaa tiedostoa, muista tehdä tallennus ja commit, ennen kuin siirryt työskentelemään seuraavan asian parissa.

Commit-viestien kirjoittaminen on oma taiteenlajinsa. Viestin tulisi kertoa selkeästi, mitä muutoksia kyseinen commit aiheuttaa ja miksi se tehdään. Esimerkiksi [Chris Beamsin ohje](https://chris.beams.io/posts/git-commit/) on hyvää luettavaa ihanteista, joihin voi pyrkiä.

Kun commitit on tehty hyvin, projektia on mukava katsella myöhemmin GitHubissa. Viesteistä voi seurata, miten projekti on kehittynyt ja mitä muutoksia on tehty milloinkin.

## Muutosten peruminen

### Paikallisen muutoksen peruminen

Tarkastellaan vielä tilannetta, jossa tiedostoa `app.py` on muutettu:

```console
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   app.py

no changes added to commit (use "git add" and/or "git commit -a")
```

Saattaa olla, että muutos oli erehdys ja haluaisimme perua sen. Voimme noudattaa yllä olevaa neuvoa ja perua muutoksen näin:

```console
$ git checkout app.py
```

Tämä komento hakee tiedoston `app.py` repositoriosta ja korvaa sillä muutetun tiedoston. Nyt työhakemiston tiedoston sisältö on taas sama kuin repositoriossa:

```console
$ git status
On branch main
nothing to commit, working tree clean
```

### Tiedosto pois commitista

Entä jos laitamme muokatun tiedoston vahingossa mukaan commitiin, mutta emme haluakaan tehdä commitia? Silloin tilanne näyttää seuraavalta:

```console
$ git add app.py
$ git status
On branch main
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   app.py
```

Tässäkin tapauksessa voimme seurata komennon antamaa neuvoa:

```console
$ git reset HEAD app.py
```

Tämän seurauksena tiedosto `app.py` poistetaan commitista ja se näkyy taas muokattuna:

```console
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   app.py

no changes added to commit (use "git add" and/or "git commit -a")
```

Vastaavasti komento `git reset HEAD` ilman tiedostoa poistaa kaikki commitiin lisätyt tiedostot ja voimme aloittaa puhtaalta pöydältä commitin valmistelut.

### Commitin peruminen

Seuraavassa tilanteessa olemme vieneet commitin loppuun ja tajuamme vasta sitten, että commit oli virhe:

```console
$ git add app.py
$ git commit -m "Change file"
[main eff67d3] Change file
 1 file changed, 1 insertion(+)
```

Tässä vaiheessa commit näkyy jo tehtyjen commitien listalla:

```console
$ git log
commit eff67d3743e37837e99b278c3843b30280e86925 (HEAD -> main)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Tue Dec 10 19:18:55 2024 +0300

    Change file

commit 7cfdfabca6b021bbe314d77b1ff0718cc415b9d5
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Tue Dec 10 17:36:10 2024 +0300

    First commit

...
```

Kuitenkin kun commit on tehty vasta paikallisesti, pystymme perumaan sen näin:

```console
$ git reset HEAD~1
```

Tämä komento siirtää repositorion tilan yhtä askelta aiemmaksi ja kaikki on taas hyvin:

```console
$ git log
commit 7cfdfabca6b021bbe314d77b1ff0718cc415b9d5 (HEAD -> main)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Tue Dec 10 17:36:10 2020 +0300

    First commit

...
```

Kuitenkin jos muutos on viety jo eteenpäin (`git push`), niin sama konsti ei toimi, koska joku toinen on saattanut käydä hakemassa tehdyn muutoksen ja peruminen siinä vaiheessa sekoittaisi pahasti asioita. Tällöin ratkaisu on tehdä uusi commit, joka peruuttaa edellisen commitin.
