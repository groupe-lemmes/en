---
layout: default
title: Glossaire
nav_order: 5
---

# Glossaire du traitement automatique de la langue
{: .no_toc }

----

Yves Ouvrard, mars 2019
{: .fs-4 .fw-300 }

Ce document peut être reproduit par n'importe quel moyen que ce soit,
pourvu qu'aucune modification ne soit effectuée et que cette notice soit
préservée.
{: .fs-4 .fw-300 }

---

* <a name="analyse_morpho">**Analyse morphologique**</a> --
L'analyse morphologique consiste à donner tous les traits morphologiques
d'une forme.  Par exemple, en français, le mot _aviez_ : deuxième
personne, pluriel, indicatif, actif.  L'analyse morphologique est
habituellement accompagnée de la lemmatisation de la forme et de son
[POS](#pos) : lemme _avoir_, verbe, 2ème personne du pluriel de l'indicatif
actif.  Souvent, un mot a plusieurs analyses morphologiques possibles. C'est le cas,
par exemple,
de la forme _avions_ pour laquelle on donnera : 
    - lemme _avoir_, verbe, 1ère personne du pluriel de l'indicatif actif.
    - lemme _avion_, nom, pluriel.

* <a name="code">**Code source**</a> -- L'ordinateur est incapable d'exécuter
des ordres exprimés en [langage naturel](#naturel) Il faut lui fournir une
suite de uns et de zéros que l'humain a le plus grand mal à lire et à
écrire. Pour obtenir un programme utilisable sur un ordinateur, le
programmeur s'exprime donc dans un [langage іnformatique](#langage) assez
ressemblant au langage naturel, mais dont le lexique est très pauvre, et la
syntaxe d'une rigueur absolue. Ce qu'il écrit alors est le **code source**
du programme.  Un programme appelé _compilateur_ transforme ensuite le code
source en code exécutable, cette suite de uns et zéros. Une autre
possibilité est d'utiliser un _langage interprété_.  Ce sera alors un
_interpréteur_ qui transforme directement le code source en instructions
exécutables par la machine.

* <a name="compilation">**compilateur, interpréteur**</a> --
Opération qui consiste à transformer le [code source](#code) en code exécutable par la machine.
Le programme chargé de la compilation est un compilateur. L'interpréteur, au lieu de générer
un exécutable, lit le code source et le transforme immédiatement en instructions exécutables.

* <a name="encodage">**encodage**</a> -- Aux débuts de l'informatique, la mémoire était limitée
et coûteuse, et l'on s'est contenté de 127 caractères, qui tenaient dans
sept bits (zéros et uns) : les chiffres, les lettres de l'alphabet latin,
majuscules et minuscules, et quelques ponctuations. Ce premier encodage, nommé ASCII 
(American Standard Code for Information Interchange), a vite été remplacé par des jeux de
caractères plus riches (255 caractères), mais qui ont le défaut d'être "localisés" 
(Europe Occidentale, Europe Centrale etc...).
On a fini par aboutir au standard Unicode, qui possède 137 929 caractères
(il a la possibilité d'en gérer plus d'un million). 
Avec les jeux de caractères "primitifs" (moins de 256 caractères),
l'encodage se faisait systématiquement sur un octet qui est, de fait,
l'élément de base pour le stockage des données.
Pour que les caractères accentués apparaissent correctement, 
il fallait être capable d'indiquer quel jeu de caractères avait été utilisé.
Avec l'adoption de l'Unicode, est apparue le problème de l'encodage : 
comment stocker une information qui aurait besoin, a priori, de 16 voire 32 bits
dans des systèmes où la brique élémentaire en compte huit ?
Plusieurs solutions, aux noms barbares (UTF-16LE, UTF-8, UTF-7), ont été proposées.
Aujourd'hui, l'UTF-8 est en passe de devenir **LE** standard.
Avant tout traitement automatique, il est prudent de connaître l'encodage du
texte à analyser. 
Tout en étant conscient que le problème se pose surtout quand interviennent
des caractères accentués ou des caractères non-latins (grecs ou cyrilliques).

* <a name="entree">**entrée (dictionnaire)**</a> --
Dans le dictionnaire, il y a en général une entrée par lemme. L'entrée débute par la [forme
canonique](#canon) du mot, suivie par des indications morphologiques (POS, génitif, $
temps primitifs), l'étymologie, les différentes traductions, des exemples,
et les formes irrégulières.

* <a name="epenthese">**épenthèse**</a> --
L'épenthèse est l'apparition, à l'intérieur d'un mot, d'une consonne destinée à faciliter 
sa prononciation. En latin médiéval, le classique _damnum_ est devenu
_dampnum_ ; _solemnitas_ est devenu _solempnitas_.

* <a name="flexion">**flexion, paradigmes, modèles**</a> --
La flexion d'un lemme est sa capacité à être écrit et prononcé de plusieurs
manières. La flexion obéit le plus souvent à un ensemble de règles qu'on
appelle [modèle](#modele). Le modèle d'un lemme est donné par le
dictionnaire, en tête d'entrée, d'une manière implicite.

* <a name="formats">**formats électroniques, encodage**</a> --
Il est devenu très facile de se procurer des textes, de toute époque et
dans toute langue. Mais pour travailler sur un texte, il faut d'abord
savoir quel est son _format_, c'est à dire quelle méthode a été utilisée
pour l'enregistrer sur une machine. Voici une liste simplifiée des formats
de texte :
    - Le texte pur, dont l'[encodage](#encodage) peut varier. De plus en plus,
  les textes sont encodés en UTF-8 ;
    - Le texte balisé (html, LaTeX, markdown) permet de changer de la couleur,
  la disposition, la taille, la police, la graisse, le style, etc., à
  n'importe quel endroit du texte. Le plus souvent, ces indications non
  textuelles sont insérées dans des balises ouvrantes et fermantes. Dans le
  format html, les balises sont les caractères \< et \>. 
    - Les fichiers issus des traitements de texte (odt LibreOffice, docx Word),
  dont les règles sont souvent très complexes, et la plupart du temps
  inutilisables tels quels par les logiciels d'analyse automatique. Pour
  remédier à cet inconvénient, il faut convertir ces fichiers en fichiers
  texte, soit grâce aux convertisseurs internes (enregistrer sous,
  exporter), soit grâce à des convertisseurs externes spécialisés.

* <a name="forme">**forme**</a> --
Une forme est l'un des éléments de la [flexion](#flexion) d'un lemme.
Lorsqu'on conjugue un verbe, on cite l'une après l'autre toutes les formes
du verbe. Chaque forme peut être étiquetée par une série de [traits
morphologiques](#trait) : genre, nombre, cas, personne, mode, temps, voix, etc.
Certaines [POS](#pos) n'ont qu'une forme, comme la préposition latine _ad_.
D'autres en ont plus d'une centaine, comme les verbes.

* <a name="canon">**Forme canonique** (ou mot-vedette, en anglais catchword)</a> --
Un [lemme](#lemme) peut avoir un très grand nombre de [formes](#forme),
mais aussi parfois quelques [variantes graphiques](#vargraph),
par exemple _negligo_ à côté de _neglego_.
Pour désigner ce lemme, on utilise l'une de ses formes, qui correspond à
une [morphologie](#morphologie) précise, choisie par consensus entre les grammairiens.
Pour le français, on a choisi le singulier des noms, le masculin singulier
des adjectifs, l'infinitif présent actif des verbes. ex. _aimer_. Pour le
latin, on donne la première personne du singulier du présent de l'indicatif
actif ex. _amo_.

* <a name="langage">**langage informatique**</a> --
Un langage informatique est un langage conçu spécialement pour être transformé
en code exécutable, le seul auquel la machine puisse obéir. Très peu
nombreux au début de l'ère informatique, ces langages se sont multipliés.
Presque tous empruntent leur lexique à l'anglais. Leur syntaxe est
extrêmement rigide, et la moindre erreur les rend inutilisables. Lorsque le
programmeur a écrit un [code source](#code), il utilise un
[compilateur](#compilation) ou un interpréteur, programmes spécialisés qui
permettent de convertir le code source en code exécutable.

* <a name="naturel">**langage naturel**</a> --
Le langage naturel est celui que les humains ont toujours utilisé pour communiquer,
alors que les [langages informatiques](#langage) ont été créés de toutes
pièces par les ingénieurs.

* <a name="lemmatiser">**Lemmatiser, lemmatiseur**</a> --
Lemmatiser un mot, c'est trouver quel [lemme](#lemme) l'a produit. Assez souvent, il 
y a plusieurs solutions, comme pour le mot _avions_, donné en exemple à l'article
[analyse morphologique](#analyse_morpho). Il y a donc deux sens à _lemmatiser_ : soit
trouver **tous** les lemmes pouvant produire une forme donnée, soit trouver **le** lemme
que l'auteur du texte a utilisé pour produire cette forme.    
La lemmatisation d'un texte se fait en plusieurs étapes :
    1. La [tokenisation](#tokenisation) consiste à transformer le texte en une liste de formes. Cette opération
    n'est pas très difficile, mais l'encodage en UTF-8 réserve parfois des surprises, en
    utilisants deux caractères pour n'en afficher qu'un.
    1. La recherche des suffixes étrangers au lemme (en latin, _-que, -ue, -ne_) ;
    1. La prise en compte de la graphie [ramiste](#ramus), des [variantes graphiques](#vargraph) 
    1. La lemmatisation proprement dite : quels lemmes peuvent donner cette forme ?
    1. En cas de réponse multiple, le classement des résultats, en commençant par le 
    plus probable.

* <a name="lemme">**lemme**</a> --
Un **lemme** est l'unité constituante d'un lexique. En latin, un lemme peut
se rencontrer sous diverses [formes](#forme), parfois très différentes les
unes des autres. Par exemple, les quatre formes _fers, ferre, latos,
tulerunt_ appartiennent au même lemme _fero_. Des [règles syntaxiques](#syntaxe)
permettent de décider quelle forme du lemme employer. Pour saisir le sens
d'un énoncé, il est indispensable de savoir identifier la
[morphologie](#morphologie) d'une forme, opération très rapide et
inconsciente la plupart du temps.

* <a name="lexicometrie">**lexicométrie**</a> --
La lexicométrie est l'étude de la quantification des lemmes dans un corpus, et de leur 
répartition. Elle est utilisée dans de nombreux buts : identifier l'auteur d'un texte,
le dater, le situer, extraire des connaissances, comparer, etc.

* <a name="modele">**Modèle**</a> --
Un modèle est un ensemble de règles qui permet de fléchir un lemme. On ne pourra donc ni conjuguer ni décliner avant de savoir quel modèle appliquer. Parmi ces règles, certaines donnent la méthode pour calculer un [radical](#radical), d'autres disent quelle [désinence](#desinence) ajouter à quel [radical](#radical) pour obtenir la forme recherchée. Un modèle reçoit le nom d'un lemme très employé appliquant ce modèle. Par exemple : _rosa, templum, amo_ Il vaut mieux que ce lemme n'ait aucune ambiguïté. Par exemple, le nom _amicus_ est aussi un adjectif. Mieux vaut choisir _lupus_, qui est toujours un nom. Les dictionnaires papier ne donnent le modèle que de manière implicite. Par exemple, au lieu de dire que le lemme _cubitum_ suit le modèle _templum_, le dictionnaire donne le génitif (i) et le genre (n.) : **cubitum**, i, n. : coude. La grammaire académique propose un nombre réduit de modèles. Les lemmatiseurs latins en utilisent plus d'une centaine. Dans la flexion des lemmes les plus courants, on trouve la plupart du temps des formes irrégulières, qui désobéissent aux règles de leur modèle.

* <a name="morphologie">**morphologie**</a> --
Liste des [traits morphologiques](#trait) caractéristiques d'une forme. Voici un tableau
simplifié des [traits morphologiques](#trait) en fonction des différents [POS](#pos), pour
la langue latine :
  - **nom** : cas, nombre
  - **pronom** : cas, genre, nombre
  - **adjectif** : cas, genre, nombre, degré
  - **adverbe** : degré
  - **verbe** : personne, nombre, temps, mode, voix.
  - **verbe, formes adjectivales** : cas, genre, nombre, temps, mode, voix    
Exemples :    
    1. _sustulisti_ : _tollo_, 2ème personne du pluriel, parfait indicatif actif ;
    1. _gestas_ : _gero_, accusatif féminin pluriel participe parfait passif.
    1. _cupidissimorum_ : _cupidus_, génitif masculin (ou neutre) pluriel, superlatif

* <a name="ocr">**OCR**</a> -- Optical Character Recognition, fr. ROC (peu utilisé)
L'OCR est un procédé qui consiste à photographier un texte, et à transformer
l'image obtenue en texte, qu'on peut àlors corriger, et envoyer dans un
lemmatiseur. L'OCR est loin d'être infaillible, et des relectures humaines
sont nécessaires pour corriger un texte _océrisé_.

* <a name="pos">**POS**</a> -- acronyme pour Part Of Speech.
En français, il n'y a pas de consensus. On trouve _catégorie grammaticale_,
_classe grammaticale_, _nature_, et même _partie du discours_. On peut définir
de deux manières le concept de classe grammaticale :
    - par les [traits morphologiques](#trait) de sa [flexion](#flexion) ;
    - par le lien du lemme avec le monde réel : chose ou être (nom), propriété (adjectif),
  prédicat (verbe).

* <a name="afffixe">**préfixe, suffixe**</a> --
Éléments constitutifs du lemme qui ѕe collent au début ou à la fin d'un
mot. Par exemple, le verbe _clamo_ peut recevoir
    - un préfixe : _declamo_
    - un suffixe : _clamito_
    - les deux : _conclamito_    
Le latin connaît un type particulier de suffixe, qui, au lieu de modifier
le sens du mot, lui ajoute un second mot :    
    - le suffixe _-que_, qui équivaut à _et_ + le mot : _rogandisque_ est une
    autre manière d'écrire _et rogandis_.
    - le suffixe _-ne_, rend la phrase interrogative.
    _Ad amicos confugiam_  Je me réfugierai auprès de mes amis.
    _ad amicosne confugiam ?_ Me réfugierai-je auprès de mes amis ?
    - le suffixe _-ue_, pour indiquer une alternative : _bis terue_ deux
    ou trois fois.

* <a name="prosodie">**prosodie, métrique, quantité, scansion, accentuation**</a> --
Le latin possède des syllabes longues et des syllabes brèves. Les mots sont
accentués en fonction de la disposition de ces longues et brèves. L'étude de
cette prosodie peut être intéressante pour étudier la poésie et les
clausules. Il est possible de scander automatiquement un texte, de l'accentuer,
et de repérer ses clausules (suite caractéristique de longues et
de brèves à la fin d'une phrase).

* <a name="radical">**radical, désinence**</a> --
Le radical est la partie du [lemme](#lemme) qui ne change pas lorsqu'on le [fléchit](#flexion).
La désinence est ce qu'il faut ajouter au radical pour obtenir une forme. Un lemme peut
avoir plusieurs radicaux. Les verbes latins en ont habituellement trois : le
radical d'infectum, le radical de perfectum, et le radical de supin. Ces radicaux sont
donnés par le dictionnaire sous forme de _temps primitifs_, et dans le cas du modèle
_amo_, on peut les calculer en suivant des règles ѕimples.

* <a name="ramus">**Ramus**</a> --
Pierre de la Ramée (1515 - 1572), outre une œuvre philosophique
considérable, est connu pour avoir systématiquement différencié les deux
prononciations des lettres _u_ et _i_. Par _iuuenis_, en graphie ramiste,
devient _juvenis_. Les manuels du secondaire et les dictionnaires sont en
graphie ramiste. La plupart des éditions critiques sont restées en graphie
ancienne.

* <a name="syntaxe">**syntaxe, analyse syntaxique**</a> --
La syntaxe d'une lange est l'ensemble des règles qui permettent de générer
un énoncé grammatical dans cette langue. L'analyse syntaxique automatique
est possible, mais obtient de moins bons résultats que [l'analyse morphologique](#analyse_morpho).

* <a name="tagueur">**tagger, tagueur**</a> -- Ou étiqueteur morpho-syntaxique.
Les lemmatiseurs classiques sont incapables, en présence de plusieurs
solutions de lemmatisation, de choisir laquelle est celle que l'auteur a
voulu employer, et que le lecteur intelligent reconnaît sans difficultés.
Aussi le lemmatiseur est souvent aidé par un tagueur, qui utilise des
statistiques obtenues à partir d'un corpus d'entraînement. C'est un lecteur
humain qui procède à un premire étiquetage, et l'ordinateur prend la suite.

* <a name="tokenisation">**tokenisation, token**</a> --
La tokenisation consiste à transformer le texte en une liste de formes, ou
_tokens_. Cette opération n'est pas très difficile, mais l'encodage en
UTF-8 réserve parfois des surprises, en utilisant deux caractères pour
n'en afficher qu'un.

* <a name="trait">**trait morphologique**</a> --
Quelle forme choisir lorsqu'on désire employer un lemme dans un énoncé ?
Par exemple, parmi les formes du lemme _beau_ \[belles, belle, beaux, beau\],
laquelle choisir dans la phrase _Que la campagne est b…_ ? Pour cela, on va
utiliser une série de traits morphologiques qui essaient de correspondre à
la réalité :    
  - le genre : _campagne_ est-il masculin ou féminin ?
  - le nombre : parle-t-on d'une ou de plusieurs campagnes ?    
Ce reflet de la réalité est très imparfait. Voici la liste des traits morphologiques
utilisés par le latin. Intentionnellement, les listes sont en ordre alphabétique :    
  - cas : _ablatif, accusatif, datif, génitif, locatif, nominatif, vocatif_
  - genre : _féminin, masculin, neutre_
  - nombre : _pluriel, singulier_
  - personne : _deuxième, première, troisième_
  - degré : _comparatif, positif, superlatif_
  - temps : _futur, futur antérieur, imparfait, parfait, plus-que-parfait, présent_
  - mode : _adjectif verbal, indicatif, gérondif, impératif, infinitif, participe, subjonctif, supin_
  - voix : _actif, passif_    
Chaque [catégorie grammaticale](#pos) utilise un ou plusieurs de ces traits morphologiques. L'article
_POS_ en donne la liste pour chaque catégorie.

* <a name="vargraph">**variante graphique**</a> --
La latin a une très longue histoire, au cours de laquelle les principes de notation
ont beaucoup évolué, principalement pour refléter l'évolution phonétique. On peut
distinguer :
  - L'**assimilation**, qui transforme deux consonnes successives en une consonne double :
    _adcedo_ devient _accedo_, _conminus_ devient _comminus_. 
  - La **contraction** est la perte d'une partie du mot qui ne se prononce
    plus : _amaueram_ devient _amaram_, _adscendo_ devient _ascendo_, _periculum periclum_.
  - une **abréviation** est la notation d'une partie du mot, le début ou la fin. _consules_
    s'écrit souvent _COSS_, _februarius_ devient _febr_. La plupart des prénoms sont abrégés. 
  - L'**agglutination** consiste à coller deux mots successifs pour n'en former qu'un :
    _et enim_ devient _etenim_, _sic ut_ devient _sicut_.
  - L'[**épenthèse**](#epenthese).
En outre, certaines voyelles se sont fermées ou ouvertes, les diphtongues
se sont simplifiées en une seule voyelle : _ameicus_ devient _amicus_,
_auorsor, auersor_.  Les consonnes aussi ont évolué : _colos_ devient
_color_, _caelebs_ s'écrit _caeleps_, etc.
Un lemmatiseur doit pouvoir identifier et traiter ces variantes graphiques.
À partir du XVI<sup>e</sup> siècle, sous l'impulsion de [Ramus](#ramus), on a ajouté
deux lettres à l'alphabet latin, _j_ et _v_, afin de distinguer les deux
prononciations du _i_ et du _u_. Dans les noms propres germaniques, la
ligature de deux _v_ successifs, _vv_, est devenue la lettre _w_.
