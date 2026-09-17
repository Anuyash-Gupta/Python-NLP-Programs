# Natural Language Processing Practicals

A collection of Python-based NLP practical programs covering fundamental concepts of **Natural Language Processing** using **NLTK, spaCy, and Regular Expressions**.

## 📌 About

This repository contains practical implementations of commonly used NLP techniques. The programs demonstrate how text can be processed, transformed, analyzed, and used to extract meaningful information.

The practicals cover:

* Sentence and Word Tokenization
* Stemming and Lemmatization
* Stop-word Removal
* Part-of-Speech (POS) Tagging
* Parsing and Chunking
* Named Entity Recognition (NER)

## 🎯 Objectives

The main goals of this repository are to:

* Understand the fundamentals of Natural Language Processing.
* Learn how text is divided into sentences and words.
* Implement stemming and lemmatization techniques.
* Understand and perform stop-word removal.
* Identify grammatical roles using POS tagging.
* Analyze sentence structure through parsing and chunking.
* Extract important entities from text using NER.
* Gain practical experience with popular NLP libraries.

## 🛠️ Technologies & Libraries

| Technology     | Purpose                                                   |
| -------------- | --------------------------------------------------------- |
| **Python 3.x** | Programming language                                      |
| **NLTK**       | Tokenization, stemming, stop-word removal and POS tagging |
| **spaCy**      | Tokenization, parsing, chunking and NER                   |
| **RegEx**      | Pattern-based parsing and chunking                        |

## 📂 Repository Structure

```text
NLP-Practicals/
│
├── 01_Tokenization.py
├── 02_Stemming_Lemmatization.py
├── 03_Stopword_Removal.py
├── 04_POS_Tagging.py
├── 05_Parsing_Chunking.py
├── 06_NER.py
│
└── README.md
```

## 📚 Practicals

### 01 — Tokenization

**File:** `01_Tokenization.py`

Tokenization divides a text into smaller units called **tokens**. These tokens can be sentences, words, or punctuation marks.

Example:

```text
Natural Language Processing is useful. It is used in AI.
```

The program demonstrates:

* Sentence tokenization using NLTK
* Word tokenization using NLTK
* Sentence tokenization using spaCy
* Word tokenization using spaCy

Key functions:

```text
sent_tokenize()
word_tokenize()
spacy.load()
doc.sents
```

### 02 — Stemming and Lemmatization

**File:** `02_Stemming_Lemmatization.py`

This practical demonstrates two techniques used to reduce different forms of words to a common representation.

**Stemming** removes word endings to produce a root-like form.

```text
playing → play
played  → play
studies → studi
```

**Lemmatization** converts a word into its meaningful dictionary form.

```text
running → run
studies → study
```

Key functions/classes:

```text
PorterStemmer()
WordNetLemmatizer()
stem()
lemmatize()
```

### 03 — Stop-word Removal

**File:** `03_Stopword_Removal.py`

Stop words are frequently occurring words that may provide limited value for certain NLP tasks.

Examples:

```text
the, is, a, an, of, and, in, to
```

The program:

1. Takes text as input.
2. Tokenizes the text.
3. Identifies stop words.
4. Removes them.
5. Displays the resulting text.

Key functions:

```text
stopwords.words()
word_tokenize()
```

> Stop-word removal is task-dependent. Words such as **"not"** may be important for applications like sentiment analysis.

### 04 — Part-of-Speech Tagging

**File:** `04_POS_Tagging.py`

POS tagging assigns a grammatical category to each word in a sentence.

Common categories include:

| Tag/Category | Meaning                   | Example   |
| ------------ | ------------------------- | --------- |
| Noun         | Person, place or thing    | book      |
| Verb         | Action or state           | run       |
| Adjective    | Describes a noun          | beautiful |
| Adverb       | Modifies a verb/adjective | quickly   |
| Pronoun      | Replaces a noun           | he        |
| Preposition  | Shows relationship        | in        |

Example:

```text
The student reads a book.
```

Possible tagging:

```text
The       → DT
student   → NN
reads     → VBZ
a         → DT
book      → NN
```

Key function:

```text
pos_tag()
```

### 05 — Parsing and Chunking

**File:** `05_Parsing_Chunking.py`

This practical focuses on understanding the grammatical structure of text and grouping related words into meaningful phrases.

For example:

```text
The intelligent student solved the problem.
```

A noun phrase can be identified as:

```text
The intelligent student
```

The program demonstrates:

* POS tagging
* RegEx-based grammar rules
* NLTK chunking
* spaCy noun phrase identification
* Basic dependency parsing

Example RegEx grammar:

```text
NP: {<DT>?<JJ>*<NN>}
```

Key concepts:

```text
RegexpParser()
parse()
noun_chunks
```

### 06 — Named Entity Recognition

**File:** `06_NER.py`

Named Entity Recognition identifies important names and entities in text and assigns them appropriate categories.

Common entity types include:

| Label  | Description                                |
| ------ | ------------------------------------------ |
| PERSON | Person's name                              |
| ORG    | Organization                               |
| GPE    | Country, city or other geopolitical entity |
| DATE   | Date or time                               |
| MONEY  | Monetary value                             |
| LOC    | Location                                   |

Example:

```text
Aditi visited Microsoft in Noida on Monday.
```

Possible result:

```text
Aditi      → PERSON
Microsoft  → ORG
Noida      → GPE
Monday     → DATE
```

Key spaCy attributes:

```text
doc.ents
ent.text
ent.label_
```

## 🔄 NLP Workflow

The practicals provide an introduction to a basic text-processing workflow:

```text
                Input Text
                    │
                    ▼
               Tokenization
                    │
                    ▼
       ┌────────────┴────────────┐
       │                         │
       ▼                         ▼
    Stemming              Stop-word Removal
       │                         │
       └────────────┬────────────┘
                    ▼
               POS Tagging
                    │
                    ▼
            Parsing / Chunking
                    │
                    ▼
           Named Entity Recognition
                    │
                    ▼
              Processed Text
```

The exact sequence may vary depending on the NLP application and its requirements.

## ⚙️ Installation

### 1. Install Python

Make sure Python 3.x is installed.

Verify it using:

```bash
python --version
```

### 2. Install Required Libraries

```bash
pip install nltk spacy
```

### 3. Download NLTK Resources

Run Python and execute:

```python
import nltk

nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
```

Additional resources may be required depending on your NLTK version.

### 4. Install the spaCy English Model

```bash
python -m spacy download en_core_web_sm
```

## ▶️ Running the Programs

Navigate to the project directory and run any program using:

```bash
python 01_Tokenization.py
```

Other programs:

```bash
python 02_Stemming_Lemmatization.py
python 03_Stopword_Removal.py
python 04_POS_Tagging.py
python 05_Parsing_Chunking.py
python 06_NER.py
```

## 📖 Concepts Covered

| No. | Practical                | Main Concept                 | Tools              |
| --: | ------------------------ | ---------------------------- | ------------------ |
|  01 | Tokenization             | Sentence & Word Tokenization | NLTK, spaCy        |
|  02 | Stemming & Lemmatization | Word Normalization           | NLTK               |
|  03 | Stop-word Removal        | Text Preprocessing           | NLTK               |
|  04 | POS Tagging              | Grammatical Classification   | NLTK               |
|  05 | Parsing & Chunking       | Sentence Structure           | NLTK, RegEx, spaCy |
|  06 | NER                      | Entity Extraction            | spaCy              |

## 🎓 Learning Outcomes

After completing these practicals, you should be able to:

* Explain basic NLP concepts.
* Tokenize text into sentences and words.
* Apply stemming and lemmatization.
* Remove stop words from documents.
* Perform POS tagging.
* Understand basic parsing and chunking.
* Extract noun phrases.
* Identify named entities using spaCy.
* Work with NLTK and spaCy.
* Understand the basic stages of NLP text processing.

## 🚀 Applications

The concepts demonstrated in this repository are useful in applications such as:

* 🤖 Chatbots and virtual assistants
* 🔎 Search engines
* 😊 Sentiment analysis
* 📝 Text classification
* 🌐 Machine translation
* 📄 Information extraction
* 🛡️ Spam detection
* ❓ Question-answering systems
* 📑 Resume and document analysis
* ✂️ Text summarization

## 👨‍💻 Author

**Aditi Panwar**

B.Tech CSE (AI)
