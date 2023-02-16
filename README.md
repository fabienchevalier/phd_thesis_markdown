# Template pour générer un mémoire universitaire depuis Markdown

**Attention, projet en cours de création, il n'est pas encore utilisable dans l'état**

- [Template pour générer un mémoire universitaire depuis Markdown](#template-pour-générer-un-mémoire-universitaire-depuis-markdown)
  - [Démarrage rapide](#démarrage-rapide)
    - [Prérequis](#prérequis)
    - [Rédiger son mémoire](#rédiger-son-mémoire)
      - [Organisation du template](#organisation-du-template)
      - [Misc](#misc)

> Ce projet est une adaptation en Français d'un template rédigé par Tom Polland. Tom Pollard et al. (2016). Template for writing a PhD thesis in Markdown. Zenodo. http://dx.doi.org/10.5281/zenodo.58490.
---
## Démarrage rapide

### Prérequis

De manière générale il nous faut :

- Une distribution LaTeX
- Un environnement Python
- Pandoc

MacOS:

``` bash
# clone repo
git clone https://github.com/fabienchevalier/phd_thesis_markdown.git

# get texlive
brew install --cask mactex

# get conda
brew install miniconda

# update tlmgr and packages
sudo tlmgr update --self

# create python env
conda create -n phd -y python=3.7 pandoc
conda activate phd

# install dependences
make install

# create output directory
mkdir output
```

### Rédiger son mémoire

#### Organisation du template

- source/ -> contient le contenu du mémoire, ainsi que le fichier de référence (.bib) et les métadonnées (.yml).
- style/ -> contient le template LaTeX du mémoire
- output/ -> le fichier généré sera disponible ici

Simplement déposer ses fichiers markdowns ordonnés dans le dossier source comme ceci:

```
xx_chapitre_1.md
xx_chapitre_2.md
```

Puis `make pdf`, le fichier généré sera dans /output.

N'oubliez pas de modifier les métadonnées dans le .yml en fonction des besoins.

#### Misc

Par défaut, lorsqu'on insère une image comme `![]()`, LaTeX la considérera comme une Figure et l'ajoutera à la table des matières des figures. Si on souhaite uniquement insérer un document graphique, on peut utiliser cette commande LaTeX:

``` latex
\includegraphics{path_to_img}
```

Insérer un saut de page:

``` latex
\newpage
```

