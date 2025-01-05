---
title: Pylint-työkalu
permalink: /pylint/
hide: true
---

# Pylint-työkalu

Pylint-työkalu antaa palautetta Python-tiedoston koodin tyylistä. Työkalua voi käyttää apuna, kun halutaan tarkastaa, noudattaako koodi Pythonin tyyliohjetta.

Tarkastellaan esimerkkinä seuraavaa koodia:

{: .code-title }
app.py
```python
from datetime import date
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    testMessage = "Heipparallaa!"
    return testMessage

@app.route("/day")
def day():
    names = ["maanantai", "tiistai", "keskiviikko","torstai",
             "perjantai", "lauantai", "sunnuntai"]
    weekday=date.today().weekday()
    return "Tänään on " + names[weekday]

@app.route("/page/<int:id>")
def page(id):
    return "Tämä on sivu " + str(id)
```

Komento `pylint *.py` tarkastaa kaikki hakemistossa olevat Python-tiedostot. Tässä tapauksessa komento antaa seuraavan raportin:

```console
$ pylint *.py
************* Module app
app.py:13:50: C0326: Exactly one space required after comma
    names = ["maanantai", "tiistai", "keskiviikko","torstai",
                                                  ^ (bad-whitespace)
app.py:15:11: C0326: Exactly one space required around assignment
    weekday=date.today().weekday()
           ^ (bad-whitespace)
app.py:1:0: C0114: Missing module docstring (missing-module-docstring)
app.py:4:0: C0103: Constant name "app" doesn't conform to UPPER_CASE naming style (invalid-name)
app.py:7:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:8:4: C0103: Variable name "testMessage" doesn't conform to snake_case naming style (invalid-name)
app.py:12:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:19:9: W0622: Redefining built-in 'id' (redefined-builtin)
app.py:19:0: C0103: Argument name "id" doesn't conform to snake_case naming style (invalid-name)
app.py:19:0: C0116: Missing function or method docstring (missing-function-docstring)

-------------------------------------------------------------------
Your code has been rated at 1.67/10
```

Raportissa näkyy lista huomautuksista sekä lopussa koodin yleisarvosana.

## Raportin läpikäynti

Käydään läpi raportissa olevat huomautukset:

```console
app.py:13:50: C0326: Exactly one space required after comma
    names = ["maanantai", "tiistai", "keskiviikko","torstai",
                                                  ^ (bad-whitespace)
```
Listassa merkin `,` jälkeen tulisi olla välilyönti.

```console
app.py:15:11: C0326: Exactly one space required around assignment
    weekday=date.today().weekday()
           ^ (bad-whitespace)
```

Sijoituksessa merkin `=` kummallakin puolella tulisi olla välilyönti.

```console
app.py:1:0: C0114: Missing module docstring (missing-module-docstring)
```

Tiedoston alussa ei ole kommenttia, joka kuvaa tiedoston sisällön (docstring).

```console
app.py:4:0: C0103: Constant name "app" doesn't conform to UPPER_CASE naming style (invalid-name)
```

Päätasolla oleva muuttuja tulkitaan vakioksi, jonka nimen tulisi olla `APP`.

```console
app.py:7:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:12:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:19:0: C0116: Missing function or method docstring (missing-function-docstring)
```

Funktion alussa ei ole kommenttia, joka kuvaa funktion sisällön (docstring).

```console
app.py:8:4: C0103: Variable name "testMessage" doesn't conform to snake_case naming style (invalid-name)
```

Muuttujan nimi `testMessage` tulisi olla `test_message`.

```console
app.py:19:9: W0622: Redefining built-in 'id' (redefined-builtin)
app.py:19:0: C0103: Argument name "id" doesn't conform to snake_case naming style (invalid-name)
```

Funktion parametrin nimi `id` peittää Pythonin `id`-funktion. Lisäksi muuttujan nimi `id` on liian lyhyt.

## Korjattu koodi

Raportissa on monia koodin tyyliin liittyviä asioita, joiden korjaaminen on helppoa. Seuraavassa on korjattu koodi:

{: .code-title }
app.py
```python
from datetime import date
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    test_message = "Heipparallaa!"
    return test_message

@app.route("/day")
def day():
    names = ["maanantai", "tiistai", "keskiviikko", "torstai",
             "perjantai", "lauantai", "sunnuntai"]
    weekday = date.today().weekday()
    return "Tänään on " + names[weekday]

@app.route("/page/<int:id>")
def page(page_id):
    return "Tämä on sivu " + str(page_id)
```

Näiden muutosten jälkeen voidaan pyytää uusi raportti:

```console
$ pylint *.py
************* Module app
app.py:1:0: C0114: Missing module docstring (missing-module-docstring)
app.py:4:0: C0103: Constant name "app" doesn't conform to UPPER_CASE naming style (invalid-name)
app.py:7:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:12:0: C0116: Missing function or method docstring (missing-function-docstring)
app.py:19:0: C0116: Missing function or method docstring (missing-function-docstring)

------------------------------------------------------------------
Your code has been rated at 5.83/10 (previous run: 1.67/10, +4.17)
```

Muutosten jälkeen raportti on selkeästi lyhempi ja koodin arvosana on parempi.

Raportissa on edelleen huomautuksia, mutta voimme olla tyytyväisiä tähän. Tällä kurssilla ei ole vaatimuksena kirjoittaa docstring-kommentteja, eikä päätasolla oleva muuttujan nimi `app` haittaa tässä tilanteessa.
