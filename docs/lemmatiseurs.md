---
layout: default
title: Lemmatizers, parameters, tools
nav_order: 4
---

# Lemmatizers, parameters, tools
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Lemmatizers and taggers

### TreeTagger
{: .mb-3 }

 The TreeTagger is a tool for annotating text with part-of-speech and lemma information. It was developed by Helmut Schmid in the TC project at the Institute for Computational Linguistics of the University of Stuttgart. The TreeTagger has been successfully used to tag German, English, French, Italian, Danish, Swedish, Norwegian, Dutch, Spanish, Bulgarian, Russian, Portuguese, Belarusian, Ukrainian, Galician, Greek, Chinese, Swahili, Slovak, Slovenian, Latin, Estonian, Polish, Persian, Romanian, Czech, Coptic and old French texts and is adaptable to other languages if a lexicon and a manually tagged training corpus are available. 

Website: [TreeTagger](https://www.cis.uni-muenchen.de/~schmid/tools/TreeTagger/){:target="_blank"}

---

### Collatinus
{: .mb-3 }

Collatinus is both a lemmatizer and a morphological analyzer for Latin texts: if given a declension or conjugation form, it can find out which word to look up in the dictionary to get its translation into another language, its different meanings, and all the other data a dictionary usually provides.

In practice, it's especially useful for Latin teachers, who can quickly give their pupils a new text with lexical support, based on a text that's not in the textbook. Students often use it to read Latin more easily when their lexical and morphological knowledge is still insufficient.

Website: [Collatinus](https://outils.biblissima.fr/fr/collatinus/){:target="_blank"}

---

### spaCy
{: .mb-3 }

spaCy is a [Python](https://fr.wikipedia.org/wiki/Python_(language)) software library for automatic language processing (NLP). It implements various linguistic annotations to provide an overview of the grammatical structure of a text (word types, parts of speech, word relationships). It performs tokenization, lemmatization, POS tagging and other advanced operations.

Website: [spaCy](https://spacy.io/usage/spacy-101){:target="_blank"}

---

### Pie (and Deucalion/Flask Pie)
{: .mb-3 }

Pie is a language independant lemmatizer implemented in python and built for "variation-rich languages" which includes Latin. It's a deep learning tool that can be trained and retrained with data in TSV format. As of 2019, it seems to be one of the state-of-the-art lemmatizers in terms of results. It can be trained jointly on morphology, POS and lemmatization tasks. 

Website: [Pie (and Deucalion/Flask Pie)](https://wiki.digitalclassicist.org/Deucalion_and_Pie_lemmatizers){:target="_blank"}

---

### StanfordNLP
{: .mb-3 }

StanfordNLP is a Python natural language analysis package. It contains tools, which can be used in a pipeline, to convert a string containing human language text into lists of sentences and words, to generate base forms of those words, their parts of speech and morphological features, and to give a syntactic structure dependency parse, which is designed to be parallel among more than 70 languages, using the Universal Dependencies formalism. In addition, it is able to call the CoreNLP Java package and inherits additonal functionality from there, such as constituency parsing, coreference resolution, and linguistic pattern matching.

Website: [StanfordNLP](https://stanfordnlp.github.io/stanfordnlp/){:target="_blank"}

---

### WordNet (nltk)
{: .mb-3 }

WordNet® is a large lexical database of English. Nouns, verbs, adjectives and adverbs are grouped into sets of cognitive synonyms (synsets), each expressing a distinct concept. Synsets are interlinked by means of conceptual-semantic and lexical relations. The resulting network of meaningfully related words and concepts can be navigated with the browser. WordNet is also freely and publicly available for download. WordNet's structure makes it a useful tool for computational linguistics and natural language processing.

Website: [WordNet](https://wordnet.princeton.edu/){:target="_blank"}

---

### TextBlob
{: .mb-3 }

TextBlob is a Python (2 and 3) library for processing textual data. It provides a simple API for diving into common natural language processing (NLP) tasks such as part-of-speech tagging, noun phrase extraction, sentiment analysis, classification, translation, and more.

Website: [TextBlob](https://textblob.readthedocs.io/en/dev/){:target="_blank"}

---

### MarMoT
{: .mb-3 }

MARMOT is a Python library for dealing with multimodal data consisting of both images and text. It does not require multimodal pretraining and it can deal with observations missing modalities. This repo is currently under construction and is in a very rough state; please feel free to reach out if you have any questions.

Website: [MarMoT](https://github.com/patrickywu/MARMOT){:target="_blank"}

---

### FastText
{: .mb-3 }

FastText is an open-source, free, lightweight library that allows users to learn text representations and text classifiers. It works on standard, generic hardware. Models can later be reduced in size to even fit on mobile devices.

Website: [FastText](https://fasttext.cc/){:target="_blank"}

---

### LGeRM
{: .mb-3 }

LGeRM (Lemmes Graphies et Règles Morphologiques, pronounced "it sprouts"), is a lemmatizer designed to manage the historical graphical variation of French. It was initially developed for Middle French (1330-1500) and then adapted to 16th and 17th century French. It can also handle modern French. 

Website: [LGeRM](http://stella.atilf.fr/LGeRM/plateforme/){:target="_blank"}

---

### UDPipe
{: .mb-3 }

UDPipe is a trainable pipeline for tokenization, tagging, lemmatization and dependency parsing of CoNLL-U files. UDPipe is language-agnostic and can be trained given annotated data in CoNLL-U format. Trained models are provided for nearly all UD treebanks. UDPipe is available as a binary for Linux/Windows/OS X, as a library for C++, Python, Perl, Java, C#, and as a web service. Third-party R CRAN package also exists. 

Website: [UDPipe](https://lindat.mff.cuni.cz/services/udpipe/){:target="_blank"}

---

### FreeLing
{: .mb-3 }

FreeLing is a C++ library providing language analysis functionalities (morphological analysis, named entity detection, PoS-tagging, parsing, Word Sense Disambiguation, Semantic Role Labelling, etc.) for a variety of languages (English, Spanish, Portuguese, Italian, French, German, Russian, Catalan, Galician, Croatian, Slovene, among others).

Website: [FreeLing](https://nlp.lsi.upc.edu/freeling/index.php/){:target="_blank"}

---

### CLTK
{: .mb-3 }

The Classical Language Toolkit (CLTK) is a Python library offering natural language processing (NLP) for the languages of pre–modern Eurasia. Pre-configured pipelines are available for 19 languages.

Website: [CLTK](http://cltk.org/){:target="_blank"}

## Parameter sets

Parameter sets and models for medieval languages, mainly Latin and Old French:

- OMNIA (Latin, especially medieval Latin; TreeTagger)
- Lasla (Latin; Pie, via the Deucalion latin + Collatinus)
- Achim Stein (Old French; TreeTagger)
- LatinCy (Latin; Spacy: [https://huggingface.co/latincy](https://huggingface.co/latincy){:target="_blank"}; [https://spacy.io/universe/project/latincy](https://spacy.io/universe/project/latincy){:target="_blank"}; [https://arxiv.org/abs/2305.04365](https://arxiv.org/abs/2305.04365){:target="_blank"})
- Deucalion (Old French; [https://zenodo.org/record/3237455](https://zenodo.org/record/3237455){:target="_blank"}; lemmas from the Tobler‑Lommatzsch +  POS from  Cattex; for Pie)
- Middle High German (Middle High German; TreeTagger)
- PALM (TreeTagger)
- Latin for TreeTagger (TreeTagger: [https://www.cis.uni-muenchen.de/~schmid/tools/TreeTagger/](https://www.cis.uni-muenchen.de/~schmid/tools/TreeTagger/){:target="_blank"})
- LiLa Lemma Bank (Latin; no special software required: [https://lila-erc.eu/lodview/data/id/lemma/LemmaBank](https://lila-erc.eu/lodview/data/id/lemma/LemmaBank){:target="_blank"})
- Old French lemmatization (Old French; TreeTagger: [https://github.com/CristinaGHolgado/old-french-lemmatization](https://github.com/CristinaGHolgado/old-french-lemmatization){:target="_blank"})
- eHumanities Desktop (Latin; MarMoT [https://www.texttechnologylab.org/applications/ehumanities-desktop/](https://www.texttechnologylab.org/applications/ehumanities-desktop/){:target="_blank"})
- Perseus TreeBank (latin; [https://github.com/PerseusDL/treebank_data/tree/master/v2.0/Latin](https://github.com/PerseusDL/treebank_data/tree/master/v2.0/Latin){:target="_blank"})
- CLTK (several ancient languages: Latin; Old English; Middle English; Middle High German; etc.: [https://legacy.cltk.org/en/latest/index.html](https://legacy.cltk.org/en/latest/index.html){:target="_blank"}) 


## Lemmatization post-processing tools

### Pyrrha
{: .mb-3 }

Pyrrha is a simple Python Flask WebApp for accelerating the post-correction of lemmatized and morpho-syntactically tagged corpora.

Website: [Pyrrha](https://dh.chartes.psl.eu/pyrrha){:target="_blank"}

[Download the Pyrrha presentation](/assets/doc/Pyrrha.zip){: .btn .btn-green .fw-300 .text-grey-lt-000 }













