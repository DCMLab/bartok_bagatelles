![Version](https://img.shields.io/github/v/release/DCMLab/bartok_bagatelles?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/bartok_bagatelles)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/bartok_bagatelles](https://github.com/DCMLab/bartok_bagatelles) and the corresponding
* documentation page [https://dcmlab.github.io/bartok_bagatelles](https://dcmlab.github.io/bartok_bagatelles)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/bartok_bagatelles/introduction).

# Béla Bartók – 14 Bagatelles, Op. 6 (A corpus of annotated scores)

The Bagatelles of Op. 6 (1908) constitute some of Bartók's earliest explorations with the techniques that would come to define his output. Namely, they evoke the Hungarian folk melodies whose study Bartók had recently undertaken (particularly in evidence in nos. 4 and 5), and utilize innovative means of destabilizing the tonal centre. For this latter reason, the annotations in this repository reflect some of the most extreme extensions of the DCML standard yet. Note, in particular, the extensive use of secondary functions to #IV, which theorist Ernő Lendvai has proposed as a surrogate tonic function in Bartók's language. 

N.B. Data extraction will display warnings in nos. 9 and 12 due to deliberately unmetered material.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/bartok_bagatelles/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [bartok_bagatelles.zip](https://github.com/DCMLab/bartok_bagatelles/releases/latest/download/bartok_bagatelles.zip)
  * [bartok_bagatelles.datapackage.json](https://github.com/DCMLab/bartok_bagatelles/releases/latest/download/bartok_bagatelles.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/bartok_bagatelles.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first Bagatelle has the following files:

* `MS3/op06n01.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/op06n01.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/op06n01.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/op06n01.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/op06n01.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/op06n01.harmonies.tsv")
notes = ms3.load_tsv("notes/op06n01.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/bartok_bagatelles/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/bartok_bagatelles/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Béla Bartók – 14 Bagatelles, Op. 6 (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## File naming convention

```regex
op(?<op>\d{2})
n(?<no>\d{2})
```

## Overview
|file_name|measures|labels|standard|annotators |reviewers|
|---------|-------:|-----:|--------|-----------|---------|
|op06n01  |      18|    28|2.3.0   |Amelia Brey|JH       |
|op06n02  |      30|    57|2.3.0   |Amelia Brey|JH       |
|op06n03  |      24|    32|2.3.0   |Amelia Brey|DK       |
|op06n04  |      12|    42|2.3.0   |Amelia Brey|DK       |
|op06n05  |      90|    28|2.3.0   |Amelia Brey|DK       |
|op06n06  |      25|    53|2.3.0   |Amelia Brey|DK       |
|op06n07  |     118|   110|2.3.0   |Amelia Brey|HB       |
|op06n08  |      32|    70|2.3.0   |Amelia Brey|DK       |
|op06n09  |      70|    86|2.3.0   |Amelia Brey|DK       |
|op06n10  |     102|   224|2.3.0   |Amelia Brey|HB       |
|op06n11  |      87|   100|2.3.0   |Amelia Brey|DK       |
|op06n12  |      44|    77|2.3.0   |Amelia Brey|DK       |
|op06n13  |      26|    42|2.3.0   |Amelia Brey|DK       |
|op06n14  |     218|   242|2.3.0   |Amelia Brey|DK       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
