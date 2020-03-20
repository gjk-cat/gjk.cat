# Návody

Tato sekce obsahuje návody a odkazy na návody týkající se problematiky __gjk.cat__

## Markdown

- [Nauč se Markdown za X minut](https://learnxinyminutes.com/docs/cs-cz/markdown/)
- [Syntaxe Markdownu - Je Čas](https://jecas.cz/markdown)
- [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Git

- [Jak na git](https://www.kutac.cz/serialy/jak-na-git)
- [Spolupráce a git](https://naucse.python.cz/lessons/git/git-collaboration-2in1/)
- [Lehký úvod do používání gitu](https://www.fi.muni.cz/pb161/navody/git)

## Přidání nového kantora

Ve složce `teachers` vytvořte nový soubor tvaru `<jmeno>.toml`.

Jako obsah na doplňte správné hodnoty do této šablony (viz cat-prep README](https://github.com/gjk-cat/cat-prep)):

```toml
jmeno = "Lukáš Hozda"         # má odpovídat jménu, které osoba používá v gitu, tj. `user.name`
email = "luk.hozda@gmail.com" # odpovídá email, který osoba používá v gitu, tj. `user.email`
username = "magnusi"          # pro kontexty, kde se nevyplatí používat email nebo jméno, např. odkazy
# libovolný popisek, formátován jako markdown, může sloužit na extra informace
# doporučuje se začínat na třetí úrovni nadpisů v zájmu přehlednosti seznamu vyučujících
bio = """
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Sed lacinia hendrerit placerat.

### Mauris posuere libero dui
non feugiat nunc imperdiet non. Ut pharetra sodales mi,
quis __sagittis__ velit __tristique__ tincidunt.[1]

### Sed in tellus tincidunt, molestie libero vel,
semper mi. Praesent lacus felis, `aliquam` in tempor vel,
fringilla eget dui. Quisque *tristique* pulvinar fringilla.

[1]: <https://www.lipsum.com/feed/html>
"""
```

## Přidání nového předmětu

Ve složce `src` vytvořte podsložku (nebo podpodsložku, dle ustanoveného systému).

Do ní přidejte soubor `subject.md` s následujícím obsahem (nahraďte za správné hodnoty):

```markdown
nazev = "Můj první předmět"
zodpovedna_osoba = "Lukáš Hozda"
# ↑ pokud možno, mělo by odpovídat jménu, emailu nebo usernamu některého vyučujícícho
#   pokud je autorem někdo jiný, zadejte email.
bio = "krátký popisek předmětu"

+++

## Můj první předmět

Lorem ipsum dolor sit amet, consectetur adipiscing elit.
In varius lacinia risus eu vehicula. Vestibulum consectetur
feugiat dignissim. Mauris sed leo id lectus commodo egestas.
Integer sed ligula quis lorem viverra fringilla lobortis at elit.
Fusce a eros laoreet, dictum enim et, pellentesque erat.

```

Nezapomeňte tento soubor zmínit v `SUMMARY.md`,
viz [mdbook dokumentace](https://phaiax.github.io/mdBook/format/summary.html)

Od teď všechny soubory, které jsou zmíněné v `SUMMARY.md`
a nalézají se u nebo v podsložkách vůči souboru `subject.md`
budou považovány za materiály patřící k tomuto předmětu.

## Přidání nového materiálu

Pro přidání nového materiálu k předmětu je zapotřebí vytvořit
nový markdownový soubor na stejné úrovni nebo v podsložce vůči souboru
`subject.md` patřícího k danému předmětu.

Poté je potřeba tento soubor zmínit kdekoliv v `SUMMARY.md`.
Kočičí hierarchie je paralelní té `mdbookové`,
takže materiály nemusí být přímo podprvky svých `subject.md` souborů.

Tento soubor má identické formátování jako ostatní kapitoly, akorát musí
mít nahoře hlavičku s TOML konfigurací.

Mohl by vypadat třeba takto:

```markdown
nazev = "Můj první článek"
tagy = ["tag1", "tag2", "tag3"]
datum = "20.1.2019"  # dobrovolné a libovolné. Jelikož "datum" je singulár  od "data", lze použít jakkoliv :^)

+++

# Můj první článek

Lorem ipsum dolor sit amet, consectetur adipiscing elit.
In varius lacinia risus eu vehicula. Vestibulum consectetur
feugiat dignissim. Mauris sed leo id lectus commodo egestas.
Integer sed ligula quis lorem viverra fringilla lobortis at elit.
Fusce a eros laoreet, dictum enim et, pellentesque erat.
```

## Mazání objektů

stačí smazat soubory

## Tvorba vlastní cat-wiki a deployment na ZEIT.co

viz [cat-prep](https://github.com/gjk-cat/cat-prep)
