# 🇷🇺 Russian Dashboard

## 📊 Vocabulary Overview

### 🔹 Verbs
```dataview
LIST
FROM "Languages/Russian/Vocabulary/Verbs"
SORT file.name ASC
```
### 🔹Imperfective verbs
```dataview
LIST
FROM "Languages/Russian/Vocabulary/Verbs"
WHERE Aspect = "Imperfective"
SORT file.name ASC
```
### 🔹Perfective verbs
```dataview
LIST
FROM "Languages/Russian/Vocabulary/Verbs"
WHERE Aspect = "Perfective"
SORT file.name ASC
```
### 🔹Accusative Verbs
```dataview
TABLE file.link AS "Verb", CasesUsed AS "Cases"
FROM "Languages/Russian/Vocabulary/Verbs"
WHERE contains(CasesUsed, "Accusative")
SORT file.name ASC

```

### 🔹Nouns
```dataview
TABLE Gender, Animacy, file.link AS "Note"
FROM "Languages/Russian/Vocabulary/Nouns"
SORT file.name ASC
```
### 🔹Adjectives
```dataview
TABLE file.link AS "Note"
FROM "Languages/Russian/Vocabulary/Adjectives"
SORT file.name ASC
```
### 🔹Expressions
```dataview
TABLE file.link AS "Note"
FROM "Languages/Russian/Vocabulary/Expressions"
SORT file.name ASC
```
