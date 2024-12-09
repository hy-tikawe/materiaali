---
title: Gitin käyttäminen
permalink: /git/
hide: true
---

# Gitin käyttäminen

Kun projektia kehitetään, omalla koneella on paikallinen projektin _työhakemisto_ sekä siihen liittyvä repositorio. Kun työhakemiston muutokset halutaan talteen repositorioon, tiedostot valitaan ensin komennolla `git add` ja sitten suoritetaan komento `git commit`.

Tämän lisäksi GitHubissa on toinen repositorio, jonka sisällön on tarkoitus olla sama kuin oman koneen repositoriossa. Komento `git push` siirtää muutoksia omalta koneelta GitHubiin, ja komento `git pull` puolestaan siirtää muutoksia GitHubista omalle koneelle.

## Projektin aloitus

Tehdään esimerkkinä projekti nimellä `tikawe-test`, jonka pohjana on materiaalin osassa 1 oleva esimerkkisovellus. Luodaan projektille hakemisto, jossa on Pythonin virtuaaliympäristö, ja lisätään projektiin kaksi tiedostoa:

```console
$ mkdir tikawe-test
$ cd tikawe-test
$ python3 -m venv venv
$ cat > app.py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return "Heipparallaa!"
(Control+D)
$ cat > README.md
TODO
(Control+D)
```

Tässä luotiin tiedostot `app.py` ja `README.md`. Tiedostossa `app.py` on sama sisältö kuin osassa 1. Tiedostossa `README.md` on pohja sovelluksen kuvaukselle.

Yllä on käytetty `cat`-komentoa tiedostojen luomiseen. Komento `cat > [nimi]` luo tiedoston `[nimi]`, minkä jälkeen voi kirjoittaa rivejä. Kun tiedoston sisältö on valmis, rivit siirtyvät tiedostoon painamalla Control+D.

Luodaan tämän jälkeen GitHubissa projektia varten repositorio nimellä `tikawe-test` oletusasetuksilla:

![](../img/github1.png)

Repositorion luomisen jälkeen GitHub antaa ohjeet, joita voimme seurata melko suoraan. Luodaan paikallinen repositorio ja tehdään ensimmäinen commit, jossa lisätään tiedostot `app.py` ja `README.md`:

```console
$ git init
Initialised empty Git repository in /tikawe-test/.git/
$ git add app.py
$ git add README.md
$ git commit -m "First commit"
[master (root-commit) 3b8f8ea] First commit
 2 files changed, 8 insertions(+)
 create mode 100644 README.md
 create mode 100644 app.py
``` 

Seuraavaksi kytketään yhteen paikallinen repositorio sekä GitHubissa oleva repositorio. Tässä `[tunnus]` tarkoittaa GitHub-tunnusta.

```console
$ git branch -M main
$ git remote add origin git@github.com:[tunnus]/tikawe-test.git
$ git push -u origin main
Enumerating objects: 4, done.
...
To github.com:[tunnus]/tikawe-test.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

Tämän jälkeen projektin pitäisi näyttää seuraavalta GitHubissa:

![](../img/github2.png)

Tarkastetaan nyt projektin tilanne komennolla `git status`:

```console
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	__pycache__/
	venv/

nothing added to commit but untracked files present (use "git add" to track)
```

Tästä näkee, että projektissa on vielä kaksi versionhallinnan ulkopuolista hakemistoa `__pycache__` ja `venv`, jotka liittyvät Python-koodin suorittamiseen ja virtuaaliympäristöön. Nämä hakemistot eivät kuulu versionhallintaan, koska ne liittyvät sovelluksen paikalliseen suorittamiseen.

Tiedostossa `.gitignore` voidaan listata tiedostot ja hakemistot, joiden tulee jäädä versionhallinnan ulkopuolelle. Tässä tapauksessa voimme luoda tiedoston seuraavasti ja lisätä sen repositorioon:

```console
$ cat > .gitignore
__pycache__
venv
(Control+D)
$ git add .gitignore
$ git commit -m "Add .gitignore"
[main 5e0c950] Add .gitignore
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore
$ git push
Enumerating objects: 4, done.
...
To github.com:[tunnus]/tikawe-test.git
   3b8f8ea..5e0c950  main -> main
```

Tämän jälkeen git tietää, että hakemistot `__pycache__` ja `venv` tulee jättää huomiotta, eikä komento `git status` näytä enää niitä:

```console
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.

nothing to commit, working tree clean
```

Tarkastetaan vielä komennon `git log` avulla repositorion tilanne:

```console
$ git log
commit 5e0c95017f89127fea233b55ed88f2f0a2aea852 (HEAD -> main, origin/main)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Mon Dec 9 16:37:08 2024 +0200

    Add .gitignore

commit 3b8f8ea11aa4c7afeae3669d1227c17541c5ad81
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Mon Dec 9 16:34:23 2024 +0200

    First commit
```

Tässä näkyvät oikealla tavalla kaksi commitia, jotka olemme tehneet. Tästä on hyvä jatkaa projektin kehittämistä.

## Projektin kehitys

Projektin kehityksen aikana hyvä tapa käyttää versionhallintaa on

Tehdään esimerkin vuoksi projektiin muutos, jossa sovellus näyttää viestin `Heipparallaa!` sijasta viestin `Tervetuloa!`. Muutos tulee tiedostoon `app.py` ja haluamme viedä muutoksen versionhallintaan.

Tarkastetaan muutoksen jälkeen projektin tilanne komennolla `git status`:

```console
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   app.py

no changes added to commit (use "git add" and/or "git commit -a")
```

Tästä näkee, että tiedosto `app.py` on muuttunut, kuten pitääkin. Komento `git diff` näyttää tarkemmin, miten tiedosto on muuttunut:

```console
$ git diff
diff --git a/app.py b/app.py
index 00cc2a0..28e40dc 100644
--- a/app.py
+++ b/app.py
@@ -4,4 +4,4 @@ app = Flask(__name__)
 
 @app.route("/")
 def index():
-    return "Heipparallaa!"
+    return "Tervetuloa!"
```

Tästä näkee, että viesti `Heipparallaa!` on muuttunut muotoon `Tervetuloa!`.

```console
$ git add app.py
$ git commit -m "Change message"
[main c83aefc] Change message
 1 file changed, 1 insertion(+), 1 deletion(-)
```


```console
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
$ git log
commit c83aefc8718cb56a129cfb710dd3271759344d63 (HEAD -> main)
Author: Antti Laaksonen <ahslaaks@cs.helsinki.fi>
Date:   Mon Dec 9 18:07:06 2024 +0200

    Change message

...
```

```console
$ git push
```

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
