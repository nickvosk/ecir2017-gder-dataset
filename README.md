## GDER dataset

This repository contains the dataset used in the ECIR 2017 paper on "Generating descriptions of entity relationships".

The subfolder in the `data` folder contain the compressed data per relationship (e.g. `isSpouseOf.zip`).

Each relationship folder contains:

- `train.json`: the *training* data (80%), 
- `test.json`: the *test* data (20%),

Each element in the files `train.json` and `test.json` has the following format:

Field | Description
--- | ---
`sentence_id` | Custom sentence id
`text_freebaseid` | Relationship description from Wikipedia. Words are lower-cased. Entities are replaced by their Freebase id.
`text_wikiid` | Relationship description from Wikipedia. Words are lower-cased. Entities are replaced by their Wikipedia id.
`text_pos` | Relationship description from Wikipedia. Words are lower-cased and POS-tagged. Entities are replaced by their Freebase id.
`EDG` | The edges list of the entity-dependency graph of the sentence.
`subj` | Subject `entity dictionary`
`obj` | Object `entity dictionary`
`med` | Mediator `entity dictionary` (might be `None`)

Each `entity dictionary` has the following format:

Field | Description
--- | ---
`id` | The Freebase id of the entity
`attributes` | The attributes of the entity
`direct_relations` | The one-hop predicates with the entity as the subject 

**Example**:

```json
{
  "sentence_id": "AVTnpAd_1AhoW2uon-iM",
  "text_freebaseid": "f_m.04yc16s is married to f_m.02hrh1q f_m.076pt5 .",
  "text_wikiid": "gloria_gwynne_gilford is married to actress Robert_Pine .",
  "text_pos": "f_m.04yc16s/ENT is/VBZ married/VBN to/TO f_m.02hrh1q/ENT f_m.076pt5/ENT ./.",
  "EDG": [
  [
  "f_m.04yc16s",
  "f_m.02hrh1q",
  "f_people.person.profession"
  ],
  [
  "f_m.04yc16s",
  "f_m.05n92s9",
  "f_people.person.spouse_s"
  ],
  [
  "f_m.076pt5",
  "f_m.02hrh1q",
  "f_people.person.profession"
  ],
  [
  "f_m.076pt5",
  "f_m.05n92s9",
  "f_people.person.spouse_s"
  ],
  [
  "f_m.05n92s9",
  "f_m.076pt5",
  "f_people.marriage.spouse"
  ],
  [
  "f_m.05n92s9",
  "f_m.04yc16s",
  "f_people.marriage.spouse"
  ],
  [
  "f_m.02hrh1q",
  "f_m.076pt5",
  "f_people.profession.people_with_this_profession"
  ],
  [
  "f_m.02hrh1q",
  "f_m.04yc16s",
  "f_people.profession.people_with_this_profession"
  ]
  ],
  "subj": {
    "attributes": [
    [
    "f_people.person.gender",
    "f_m.02zsn"
    ],
    [
    "f_people.person.profession",
    "f_m.06796"
    ],
    [
    "f_people.person.nationality",
    "f_m.09c7w0"
    ],
    [
    "f_people.person.profession",
    "f_m.02hrh1q"
    ]
    ],
    "id": "f_m.04yc16s",
    "direct_relations": [
    [
    "fk_wikipedia.en_id",
    "20052072"
    ],
    [
    "f_people.person.children",
    "f_m.0bb_pcr"
    ],
    [
    "f_people.person.children",
    "f_m.0c6g1l"
    ],
    [
    "f_people.person.date_of_birth",
    "1946-07-27^^<http://www.w3.org/2001/XMLSchema#date>"
    ],
    [
    "f_people.person.gender",
    "f_m.02zsn"
    ],
    [
    "f_people.person.nationality",
    "f_m.09c7w0"
    ],
    [
    "f_people.person.parents",
    "f_m.05n8xsg"
    ],
    [
    "f_people.person.parents",
    "f_m.09rxfb"
    ],
    [
    "f_people.person.place_of_birth",
    "f_m.030qb3t"
    ],
    [
    "f_people.person.profession",
    "f_m.02hrh1q"
    ],
    [
    "f_people.person.profession",
    "f_m.06796"
    ],
    [
    "f_people.person.sibling_s",
    "f_m.0py3f54"
    ]
    ]
    },
    "med": {
      "attributes": [
      [
      "f_people.marriage.type_of_union",
      "f_m.04ztj"
      ]
      ],
      "id": "f_m.05n92s9",
      "direct_relations": [
      [
      "f_people.marriage.from",
      "1969-09-06^^<http://www.w3.org/2001/XMLSchema#date>"
      ],
      [
      "f_people.marriage.spouse",
      "f_m.04yc16s"
      ],
      [
      "f_people.marriage.spouse",
      "f_m.076pt5"
      ],
      [
      "f_people.marriage.type_of_union",
      "f_m.04ztj"
      ]
      ]
      },
      "obj": {
        "attributes": [
        [
        "f_people.person.profession",
        "f_m.0np9r"
        ],
        [
        "f_people.person.profession",
        "f_m.02hrh1q"
        ],
        [
        "f_people.person.gender",
        "f_m.05zppz"
        ],
        [
        "f_people.person.nationality",
        "f_m.09c7w0"
        ]
        ],
        "id": "f_m.076pt5",
        "direct_relations": [
        [
        "fk_wikipedia.en_id",
        "2363773"
        ],
        [
        "f_people.person.children",
        "f_m.0bb_pcr"
        ],
        [
        "f_people.person.children",
        "f_m.0c6g1l"
        ],
        [
        "f_people.person.date_of_birth",
        "1941-07-10^^<http://www.w3.org/2001/XMLSchema#date>"
        ],
        [
        "f_people.person.gender",
        "f_m.05zppz"
        ],
        [
        "f_people.person.height_meters",
        "1.8"
        ],
        [
        "f_people.person.nationality",
        "f_m.09c7w0"
        ],
        [
        "f_people.person.parents",
        "f_m.0j9knd2"
        ],
        [
        "f_people.person.parents",
        "f_m.0j9knd8"
        ],
        [
        "f_people.person.place_of_birth",
        "f_m.02_286"
        ],
        [
        "f_people.person.profession",
        "f_m.02hrh1q"
        ],
        [
        "f_people.person.profession",
        "f_m.0np9r"
        ]
        ]
      }
    }


```


If you use this dataset, please cite the following paper:
```
@inproceedings{voskarides-generating-2017,
Author = {Voskarides, Nikos and Meij, Edgar and de Rijke, Maarten},
Booktitle = {ECIR 2017: 39th European Conference on Information Retrieval},
Date-Added = {2016-12-02 21:40:45 +0000},
Date-Modified = {2016-12-02 21:41:31 +0000},
Month = {April},
Publisher = {Springer},
Series = {LNCS},
Title = {Generating descriptions of entity relationships},
Year = {2017}}
```
