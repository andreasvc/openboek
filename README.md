# The OpenBoek corpus

[OpenBoek](http://andreasvc.github.io/openboek/) is a corpus of public domain Dutch literature
with several layers of linguistic annotations.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />
<span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Dataset" property="dct:title" rel="dct:type">OpenBoek</span> is licensed under a
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Annotations:

- coref: exported files in [CoNLL 2012 format](http://conll.cemantix.org/2012/data.html).
  The coreference column is manually corrected. The POS, parse bit, and NER
  columns are extracted from the automatically derived parse trees.
  Annotations follow the [dutchcoref guidelines](https://github.com/andreasvc/dutchcoref/)
- parses: parse trees produced by [Alpino](http://www.let.rug.nl/vannoord/alp/Alpino/),
  one XML file per sentence. Not manually corrected. These are the parse trees for the
  original, non-normalized spelling.
- features: tab-separated files with entity features: gender and number.
  Each entity is identified by the indices (sentence number, begin/end token)
  of its first mention.
  Gender has values:
  - f (female)
  - m (male)
  - fm (unknown or mixed gender)
  - n (neuter, non-human)

  Any gender except n implies a human entity.

  Number:
  - sg (singular)
  - pl (plural; an entity consisting of multiple individuals/objects)

  The semantic number is annotated (e.g., "the group" is plural since it could be
  referred to by "they"), regardless of the syntactic number.
- spelling: manually corrected spelling, based on automatic spelling normalization by
  https://github.com/gertjanvannoord/oudeboeken
  The input is in a format understood by the Alpino parser.
- tokenized: one sentence per line of space-separated words, prefixed with an
  sentence identifier of the form parno-sentno. Used as input for Alpino and
  the spelling normalization tool. Mostly the original text, except for some
  manual spelling changes applied to Multatuli (y -> ij) and Nescio (eg., datti -> dat -ie).
- pos: manually corrected POS tags (CGN coarse tags).

## Corpus

All texts in the corpus are public domain texts from Project Gutenberg, and
includes classic Dutch texts as well as translated novels. Each fragment is at
least the first 10,000 words from the text; the total annotated dataset
contains about 103,000 tokens.

|Gutenberg ID|Date|Author|Title|
|---|---|---|---|
| PG1399  | 1877 | Leo Tolstoy        | Anna Karenina                          |
| PG37316 | 1862 | Victor Hugo        | De ellendigen                          |
| PG11318 | 1872 | Jules Verne        | De reis om de wereld in tachtig dagen  |
| PG29719 | 1911 | Nescio             | De uitvreter                           |
| PG29719 | 1918 | Nescio             | Dichtertje                             |
| PG29719 | 1915 | Nescio             | Titaantjes                             |
| PG19563 | 1889 | Louis Couperus     | Eline Vere                             |
| PG11024 | 1860 | Multatuli          | Max Havelaar                           |
| PG30933 | 1890 | Arthur Conan Doyle | Sherlock Holmes en de Agra-schat       |

