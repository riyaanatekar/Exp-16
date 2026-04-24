Aim
To study and implement various Natural Language Processing (NLP) techniques on text data using Python with the help of the NLTK (Natural Language Toolkit) library.
The experiment focuses on preprocessing and analyzing text using functions such as tokenization, stop word removal, stemming, lemmatization, part-of-speech tagging, and word frequency counting.

Theory
Introduction to NLP
Natural Language Processing (NLP) is a branch of Artificial Intelligence that enables computers to understand, process, and analyze human language.
It is used in applications such as chatbots, translation systems, sentiment analysis, speech recognition, text summarization, and search engines.
Python provides many libraries for NLP, among which NLTK is one of the most popular. It contains tools for text preprocessing, classification, tagging, parsing, and semantic reasoning.

Functions and Concepts Used in the Experiment

1. Importing NLTK and Downloading Required Resources
import nltknltk.download('punkt')nltk.download('stopwords')nltk.download('wordnet')nltk.download('punkt_tab')nltk.download('averaged_perceptron_tagger')nltk.download('averaged_perceptron_tagger_eng')
Theory:
Before using NLP tools in NLTK, required datasets and tokenizers must be downloaded.
Functions Used:
nltk.download()
Used to download specific language resources.
'punkt' → Used for word and sentence tokenization
'stopwords' → Collection of common stop words
'wordnet' → Lexical database for lemmatization
'averaged_perceptron_tagger' → POS tagging model

2. Word Tokenization
from nltk.tokenize import word_tokenizetext = "Natural language processing is interesting"tokens = word_tokenize(text)print(tokens)
Theory:
Tokenization is the process of splitting text into smaller units called tokens. Tokens may be words, punctuation marks, or symbols.
Function Used:
word_tokenize(text)
Breaks a sentence into individual words.
Example Output:
['Natural', 'language', 'processing', 'is', 'interesting']
Uses:
Text preprocessing
Search engines
Machine learning models

3. Sentence Tokenization
from nltk.tokenize import sent_tokenizetext = "Python is easy. It is widely used in data science."sentences = sent_tokenize(text)print(sentences)
Theory:
Sentence tokenization divides a paragraph into separate sentences.
Function Used:
sent_tokenize(text)
Splits text wherever sentence boundaries occur.
Example Output:
['Python is easy.', 'It is widely used in data science.']
Uses:
Text summarization
Sentence analysis
Translation systems

4. Stop Word Removal
from nltk.corpus import stopwordsstop_words = set(stopwords.words('english'))words = word_tokenize(text)filtered_words = [w for w in words if w.lower() not in stop_words]print(filtered_words)
Theory:
Stop words are common words that usually do not add important meaning, such as:
is
the
and
in
of
a
These words are removed to improve text analysis.
Functions Used:
stopwords.words('english')
Returns list of English stop words.
set()
Used for faster searching.
word_tokenize(text)
Converts sentence into words.

Example Output:
['Python', 'easy', '.', 'widely', 'used', 'data', 'science']
Uses:
Search engines
Keyword extraction
Sentiment analysis

5. Stemming
from nltk.stem import PorterStemmerstemmer = PorterStemmer()words = ["playing","studies","running","gone","watching","coding"]for w in words:    print(stemmer.stem(w))

Theory:
Stemming reduces a word to its root/base form by removing suffixes.
Examples:
playing → play
running → run
coding → code
It may not always return a valid dictionary word.

Functions Used:
PorterStemmer()
Creates a stemming object.
stemmer.stem(word)
Returns stemmed form.

Uses:
Search optimization
Text mining
Information retrieval

6. Lemmatization
from nltk.stem import WordNetLemmatizerlemmatizer
 = WordNetLemmatizer()print(lemmatizer.lemmatize("writing"))print(lemmatizer.lemmatize("studies"))print(lemmatizer.lemmatize("best"))print(lemmatizer.lemmatize("running"))print(lemmatizer.lemmatize("coding"))

Theory:
Lemmatization converts words into their meaningful dictionary base form called lemma.
Unlike stemming, it gives grammatically correct words.

Examples:
studies → study
writing → writing / write
running → running / run

Functions Used:
WordNetLemmatizer()
Creates lemmatizer object.
lemmatizer.lemmatize(word)
Returns dictionary root word.

Uses:
Grammar correction
Text understanding
Chatbots

7. Part-of-Speech (POS) Tagging
from nltk import pos_tagwords = word_tokenize("Python is a powerful programming language")pos_tags = pos_tag(words)print(pos_tags)
Theory:
POS tagging identifies grammatical roles of words in a sentence.

Examples:
Noun (NN)
Verb (VB)
Adjective (JJ)
Adverb (RB)

Function Used:
pos_tag(words)
Assigns grammar tags to each token.

Example Output:
[('Python', 'NNP'), ('is', 'VBZ'), ('a', 'DT'), ('powerful', 'JJ'), ('programming', 'NN'), ('language', 'NN')]

Uses:
Grammar checking
Parsing
Speech recognition

8. Word Frequency Count
from nltk.probability import FreqDistwords = word_tokenize(text)fd = FreqDist(words)print(fd.most_common())

Theory:
Frequency distribution counts how many times each word appears in text.

Functions Used:
FreqDist(words)
Creates frequency distribution.
most_common()
Returns words sorted by highest frequency.
Example Output:
[('Python',1), ('is',1), ('easy',1), ...]

Uses:
Keyword extraction
Trend analysis
Text statistics
Libraries Used
NLTK → Main NLP library
nltk.tokenize → Tokenization
nltk.corpus → Stopwords dataset
nltk.stem → Stemming and Lemmatization
nltk.probability → Frequency count

Conclusion
Thus, the experiment on NLP Techniques on Text Data in Python was successfully performed using the NLTK library. 
Various important NLP preprocessing methods were studied and implemented, including word tokenization, sentence tokenization, 
stop word removal, stemming, lemmatization, POS tagging, and frequency distribution.
These techniques help in cleaning, understanding, and analyzing textual data efficiently.
NLP plays a major role in modern applications such as chatbots, translators, recommendation systems, and sentiment analysis.
