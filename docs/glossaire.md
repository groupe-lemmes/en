---
layout: default
title: Glossary
nav_order: 5
---

# Automatic language processing glossary
{: .no_toc }

----

Yves Ouvrard, March 2019
{: .fs-4 .fw-300 }

This document may be reproduced by any means,
provided that no modifications are made and that this notice is
preserved.
{: .fs-4 .fw-300 }

---

* <a name="morpho_analysis">**Morphological analysis**</a> --
The morphological analysis consists in giving all the morphological traits
of a form. For example, in French, the word _aviez_: second
person, plural, indicative, active. The morphological analysis is
usually accompanied by the lemmatization of the form and its
[POS](#pos): lemma _avoir_, verb, 2nd person plural indicative
asset. Often a word has several possible morphological analyses. It's the case,
For example,
of the form _avions_ for which we will give:
     - lemma _avoir_, verb, 1st person plural of the active indicative.
     - lemma _plane_, noun, plural.

* <a name="code">**Source Code**</a> -- Computer is unable to run
orders expressed in [natural language](#natural) It must be provided with a
sequence of ones and zeros that humans have the greatest difficulty in reading and
to write. To obtain a program that can be used on a computer, the
programmer therefore expresses himself in a [computer language](#language) quite
resembling natural language, but whose lexicon is very poor, and the
syntax of absolute rigor. What he writes then is the **source code**
from the program. A program called _compiler_ then transforms the code
source into executable code, this sequence of ones and zeros. Another one
possibility is to use an _interpreted language_. It will then be a
_interpreter_ which transforms source code directly into instructions
machine executable.

* <a name="compilation">**compiler, interpreter**</a> --
Operation which consists in transforming the [source code](#code) into code executable by the machine.
The program responsible for compiling is a compiler. The interpreter, instead of generating
an executable, reads the source code and immediately turns it into executable instructions.

* <a name="encoding">**encoding**</a> -- In the early days of computing, memory was limited
and expensive, and we contented ourselves with 127 characters, which fit in
seven bits (zeros and ones): numbers, letters of the Latin alphabet,
upper and lower case, and some punctuation. This first encoding, named ASCII
(American Standard Code for Information Interchange), was quickly replaced by games of
richer characters (255 characters), but which have the defect of being "localized"
(Western Europe, Central Europe etc...).
We ended up with the Unicode standard, which has 137,929 characters
(it has the ability to manage more than a million).
With "primitive" character sets (less than 256 characters),
the encoding was done systematically on one byte which is, in fact,
the basic element for data storage.
For accented characters to appear correctly,
it needed to be able to tell which character set was used.
With the adoption of Unicode, the problem of encoding appeared:
how to store information that would need, a priori, 16 or even 32 bits
in systems where the building block has eight?
Several solutions, with barbaric names (UTF-16LE, UTF-8, UTF-7), have been proposed.
Today, UTF-8 is on its way to becoming **THE** standard.
Before any automatic processing, it is prudent to know the encoding of the
text to analyze.
While being aware that the problem arises above all when
accented characters or non-Latin characters (Greek or Cyrillic).

* <a name="entry">**entry (dictionary)**</a> --
In the dictionary, there is usually one entry per lemma. The entry begins with the [form
canonical](#canon) of the word, followed by morphological indications (POS, genitive, $
primitive times), etymology, different translations, examples,
and irregular shapes.

* <a name="epenthesis">**epenthesis**</a> --
Epenthesis is the appearance, within a word, of a consonant intended to facilitate
his pronunciation. In Medieval Latin, the classic _damnum_ became
_dampnum_; _solemnitas_ became _solempnitas_.

* <a name="flexion">**flexion, paradigms, models**</a> --
The inflection of a lemma is its ability to be written and pronounced in several
manners. Inflection most often obeys a set of rules that we
calls [model](#model). The model of a lemma is given by the
dictionary, at the head of the entry, in an implicit way.

* <a name="formats">**electronic formats, encoding**</a> --
It has become very easy to obtain texts, from all periods and
in any language. But to work on a text, you must first
know what its _format_ is, i.e. which method was used
to save it on a machine. Here is a simplified list of formats
of text:
     - Pure text, whose [encoding](#encoding) may vary. More and more,
   the texts are encoded in UTF-8;
     - Tagged text (html, LaTeX, markdown) allows to change color,
   layout, size, font, weight, style, etc., to
   anywhere in the text. Most often, these indications not
   text are inserted into opening and closing tags. In the
   html format, the tags are the characters \< and \>.
     - Files from word processors (odt LibreOffice, docx Word),
   whose rules are often very complex, and most of the time
   unusable as such by automatic analysis software. For
   remedy this drawback, it is necessary to convert these files into files
   text, or thanks to the internal converters (save as,
   export), or through specialized external converters.

* <a name="form">**form**</a> --
A form is one of the elements of the [flexion](#flexion) of a lemma.
When we conjugate a verb, we cite one after the other all the forms
of the verb. Each form can be labeled by a series of [lines
morphological](#trait): gender, number, case, person, mode, tense, voice, etc.
Some [POS](#pos) have only one form, like the Latin preposition _ad_.
Others have more than a hundred, like verbs.

* <a name="canon">**Canonical form** (or catchword)</a> --
A [lemma](#lemma) can have a very large number of [shapes](#shape),
but also sometimes some [variant graphics](#vargraph),
for example _negligo_ next to _neglego_.
To designate this lemma, we use one of its forms, which corresponds to
a precise [morphology](#morphology), chosen by consensus between grammarians.
For French, we chose the singular of nouns, the masculine singular
adjectives, the active present infinitive of verbs. ex. _to like_. For the
Latin, we give the first person singular of the present indicative
active eg. _amo_.

* <a name="language">**computer language**</a> --
A computer language is a language designed specifically to be transformed
into executable code, the only one the machine can obey. Very little
numerous at the beginning of the computer age, these languages have multiplied.
Almost all borrow their lexicon from English. Their syntax is
extremely rigid, and the slightest error renders them unusable. When the
programmer wrote a [source code](#code), he uses a
[compiler](#compilation) or an interpreter, specialized programs that
convert source code into executable code.

* <a name="natural">**natural language**</a> --
Natural language is what humans have always used to communicate.
whereas the [computer languages](#language) were created from all
parts by engineers.

* <a name="lemmatize">**Lemmatize, lemmatizer**</a> --
To lemmatize a word is to find which [lemma](#lemma) produced it. Quite often it
there are several solutions, as for the word _avions_, given as an example in the article
[morphological analysis](#analyse_morpho). There are therefore two meanings to _lemmatize_: either
find **all** the lemmas that can produce a given form, or find **the** lemma
that the author of the text used to produce this form.
The lemmatization of a text is done in several steps:
     1. [Tokenization](#tokenization) is transforming text into a list of shapes.
     1. The search for suffixes foreign to the lemma (in Latin, _-que, -ue, -ne_);
     1. Taking into account the [ramiste](#ramus) spelling, [graphic variants](#vargraph)
     1. Lemmatization itself: what lemmas can give this form?
     1. In case of multiple answers, the ranking of the results, starting with the more likely.

* <a name="lemma">**lemma**</a> --
A **lemma** is the constituent unit of a lexicon. In Latin, a lemma can
meet in various [forms](#forme), sometimes very different
each other. For example, the four forms _fers, ferre, latos,
tulerunt_ belong to the same lemma _fero_. [syntactic rules](#syntax)
allow you to decide which form of the lemma to use. To grasp the meaning
of a statement, it is essential to know how to identify the
[morphology](#morphology) of a shape, very fast operation and
mostly unconscious.

* <a name="lexicometry">**lexicometry**</a> --
Lexicometry is the study of the quantification of lemmas in a corpus, and of their
distribution. It is used for many purposes: to identify the author of a text,
date it, locate it, extract knowledge, compare, etc.

* <a name="model">**Model**</a> --
A model is a set of rules that allows to inflect a lemma. We can therefore neither conjugate nor decline before knowing which model to apply. Among these rules, some give the method to calculate a [radical](#radical), others say which [ending](#desinence) to add to which [radical](#radical) to obtain the desired form. A model receives the name of a widely used lemma applying this model. For example: _rosa, templum, amo_ It is better that this lemma has no ambiguity. For example, the noun _amicus_ is also an adjective. Better to choose _lupus_, which is still a noun. Paper dictionaries give the model only implicitly. For example, instead of saying that the lemma _cubitum_ follows the pattern _templum_, the dictionary gives the genitive (i) and the gender (n.): **cubitum**, i, n. : elbow. Academic grammar offers a reduced number of models. Latin lemmatizers use more than a hundred. In the inflection of the most common lemmas, one finds most of the time irregular forms, which disobey the rules of their model.

* <a name="morphology">**morphology**</a> --
List of characteristic [morphological traits](#trait) of a shape. Here is a table
simplified [morphological traits](#trait) according to the different [POS](#pos), for
the Latin language:
   - **name**: case, number
   - **pronoun**: case, gender, number
   - **adjective**: case, gender, number, degree
   - **adverb**: degree
   - **verb**: person, number, tense, mode, voice.
   - **verb, adjectival forms**: case, gender, number, tense, mood, voice
Examples:
     1. _sustulisti_: _tollo_, 2nd person plural, perfect active indicative;
     1. _gestas_: _gero_, accusative feminine plural perfect passive participle.
     1. _cupidissimorum_: _cupidus_, masculine genitive (or neuter) plural, superlative

* <a name="ocr">**OCR**</a> -- Optical Character Recognition, en. ROC (little used)
OCR is a process that consists of photographing a text, and transforming
the image obtained in text, which can then be corrected, and sent in a
lemmatizer. OCR is far from foolproof, and human proofreading
are needed to correct _ocerized_ text.

* <a name="pos">**POS**</a> -- acronym for Part Of Speech.
In French, there is no consensus. We find _grammatical category_,
_grammatical class_, _nature_, and even _part of speech_. We can define
the concept of grammatical class in two ways:
     - by the [morphological traits](#trait) of its [flexion](#flexion);
     - by the link of the lemma with the real world: thing or being (noun), property (adjective),
   predicate (verb).

* <a name="affix">**prefix, suffix**</a> --
Constituent elements of the lemma which ѕe stick at the beginning or at the end of a
word. For example, the verb _clamo_ can receive
     - a prefix: _declamo_
     - a suffix: _clamito_
     - both: _conclamito_
Latin knows a particular type of suffix, which, instead of modifying
meaning of the word, adds a second word to it:
     - the suffix _-que_, which is equivalent to _et_ + the word: _rogandisque_ is a
     another way of writing _et rogandis_.
     - the suffix _-ne_, makes the sentence interrogative.
     _Ad amicos confugiam_ I will take refuge with my friends.
     _ad amicosne confugiam?_ Shall I take refuge with my friends?
     - the suffix _-ue_, to indicate an alternative: _bis terue_ deux
     or three times.

* <a name="prosody">**prosody, meter, amount, scansion, accent**</a> --
Latin has long syllables and short syllables. The words are
accented depending on the arrangement of these long and short. The study of
this prosody can be interesting for studying poetry and
clauses. It is possible to automatically chant a text, to accentuate it,
and locate its clauses (characteristic sequence of long and
breves at the end of a sentence).

* <a name="radical">**radical, ending**</a> --
The radical is the part of the [lemma](#lemma) that does not change when it is [inflected](#flexion).
The ending is what must be added to the radical to obtain a form. A lemma can
have multiple radicals. Latin verbs usually have three: le
infectum radical, the perfectum radical, and the supine radical. These radicals are
given by the dictionary in the form of _primitive times_, and in the case of the model
_amo_, they can be calculated by following simple rules.

* <a name="ramus">**Ramus**</a> --
Pierre de la Ramée (1515 - 1572), in addition to a philosophical work
considerable, is known to have systematically differentiated the two
pronunciations of the letters _u_ and _i_. By _iuuenis_, in ramist script,
becomes _juvenis_. Secondary textbooks and dictionaries are in
ramist spelling. Most of the critical editions remained in spelling
Ancient.

* <a name="syntax">**syntax, parsing**</a> --
The syntax of a language is the set of rules which make it possible to generate
a grammatical statement in that language. Automatic parsing
is possible, but obtains worse results than [morphological analysis](#analyse_morpho).

* <a name="tagger">**tagger, tagger**</a> -- Or morpho-syntactic tagger.
Classical lemmatizers are incapable, in the presence of several
lemmatization solutions, to choose which is the one that the author has
wanted to use, and which the intelligent reader recognizes without difficulty.
Also the lemmatizer is often helped by a tagger, who uses
statistics obtained from a training corpus. He's a reader
human who proceeds to a first labeling, and the computer takes over.

* <a name="tokenization">**tokenization, token**</a> --
Tokenization consists of transforming the text into a list of shapes, or
_tokens_.

* <a name="trait">**morphological trait**</a> --
Which form to choose when we want to use a lemma in a statement?
For example, among the forms of the lemma _beau_ \[belles, belle, beaux, beau\],
which one to choose in the sentence _That the campaign is b…_? For this, we will
use a series of morphological traits that try to match
reality :
   - the gender: is _countryside_ masculine or feminine?
   - the number: are we talking about one or more campaigns?
This reflection of reality is very imperfect. Here is the list of morphological traits
used by Latin. Intentionally, the lists are in alphabetical order:
   - case: _ablative, accusative, dative, genitive, locative, nominative, vocative_
   - gender: _feminine, masculine, neutral_
   - number: _plural, singular_
   - person: _second, first, third_
   - degree: _comparative, positive, superlative_
   - tense: _future, past future, imperfect, perfect, pluperfect, present_
   - mode: _verbal adjective, indicative, gerund, imperative, infinitive, participle, subjunctive, supine_
   - voice: _active, passive_
Each [grammatical category](#pos) uses one or more of these morphological features. The article
_POS_ lists them for each category.

* <a name="vargraph">**graphic variant**</a> --
Latin has a very long history, during which the principles of notation
have evolved a lot, mainly to reflect phonetic evolution. We can
distinguish :
   - **Assimilation**, which transforms two successive consonants into a double consonant:
     _adcedo_ becomes _accedo_, _conminus_ becomes _comminus_.
   - The **contraction** is the loss of a part of the word which is not pronounced
     plus: _amaueram_ becomes _amaram_, _adscendo_ becomes _ascendo_, _periculum periclum_.
   - an **abbreviation** is the notation of part of the word, the beginning or the end. _consulates_
     is often written _COSS_, _februarius_ becomes _febr_. Most first names are abbreviated.
   - **Agglutination** consists of joining two successive words to form one:
     _and enim_ becomes _etenim_, _sic ut_ becomes _sicut_.
   - The [**epenthesis**](#epenthesis).
Also, some vowels closed or opened, diphthongs
simplified into a single vowel: _ameicus_ becomes _amicus_,
_auorsor, auersor_. The consonants have also evolved: _colos_ becomes
_color_, _caelebs_ is written _caeleps_, etc.
A lemmatizer must be able to identify and process these graphic variants.
From the 16<sup>th</sup> century, at the instigation of [Ramus](#ramus), we added
two letters in the Latin alphabet, _j_ and _v_, in order to distinguish the two
pronunciations of _i_ and _u_. In Germanic proper names, the
ligature of two successive _v_, _vv_, has become the letter _w_.