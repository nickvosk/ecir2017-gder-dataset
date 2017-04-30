## GDER dataset

This repository contains the dataset used in the ECIR 2017 paper on "Generating descriptions of entity relationships".

The directory `data` contains the data per relationship (e.g. `isSpouseOf`).

Each relationship folder contains:

- `train.json`: the *training* data, 
- `test.json`: the *test* data,

Each element in the files `train.json` and `test.json` has the following format:

Field | Description
--- | ---
`sentence_id` | custom sentence id
`subj_id` | Freebase id of the subject entity
`obj_id` | Freebase id of the object entity
`text` | Relationship description from Wikipedia. Words are lower-cased and POS-tagged. Entities are replaced by their freebase id.
`edges` | The edges list of the entity-dependency graph of the sentence.

**Example**:

```json
{
    "sentence_id": "AVTnooDT1AhoW2uomUkc",
    "subj_id": "f_m.04w0_f1",
    "obj_id": "f_m.06cgy",
    "text": "f_m.04w0_f1/ENT has/VBZ been/VBN married/VBN to/TO f_m.02hrh1q/ENT f_m.06cgy/ENT since/IN 1997/ENT ./.",
    "edges": [
      [
        "f_m.06cgy",
        "f_m.02hrh1q",
        "f_people.person.profession"
      ],
      [
        "f_m.06cgy",
        "f_m.04w0_dy",
        "f_people.person.spouse_s"
      ],
      [
        "f_m.04w0_dy",
        "f_m.04w0_f1",
        "f_people.marriage.spouse"
      ],
      [
        "f_m.04w0_dy",
        "f_m.06cgy",
        "f_people.marriage.spouse"
      ],
      [
        "f_m.04w0_dy",
        "1997",
        "f_people.marriage.from"
      ],
      [
        "f_m.02hrh1q",
        "f_m.06cgy",
        "f_people.profession.people_with_this_profession"
      ],
      [
        "f_m.02hrh1q",
        "f_m.04w0_f1",
        "f_people.profession.people_with_this_profession"
      ],
      [
        "f_m.04w0_f1",
        "f_m.02hrh1q",
        "f_people.person.profession"
      ],
      [
        "f_m.04w0_f1",
        "f_m.04w0_dy",
        "f_people.person.spouse_s"
      ],
      [
        "f_m.04w0_f1",
        "f_m.04w0_dy",
        "f_people.person.spouse_s"
      ]
    ]
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
