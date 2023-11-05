# Experiment-8---Implementation-of-Semantic-Analysis

## Aim : Construct a python program to read a text from a file.Identify the verbs from the text file and provide synonyms for all verbs using Natutal Language Processing 

## Algorithm:
Install the required libraries.

Install nltk (Natural Language Toolkit) by running pip install nltk in your terminal.

Install WordNet by running nltk.download('wordnet') in your Python script or notebook.

Import the necessary libraries and modules.

Read the text file.

Tokenize the text into sentences and words.

Identify verbs using part-of-speech tagging.

Get synonyms for each verb.

Process the text file and display the verbs and their synonyms.

## Program:
```
# Reg.no: 212222230065
# Name: Kavya K
```
```python
import nltk
from nltk.corpus import wordnet

nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')

def get_synonyms(word):
    synonyms = set()
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.add(lemma.name())
    return synonyms

def process_text_file(file_path):
    with open(file_path, 'r') as file:
        text = file.read()
    return text  # Return the processed text

text = process_text_file('/content/text.txt')

# Tokenize the text into sentences
sentences = nltk.sent_tokenize(text)

for sentence in sentences:
    # Tokenize each sentence into words
    words = nltk.word_tokenize(sentence)

    # Perform part-of-speech tagging
    pos_tags = nltk.pos_tag(words)

    # Extract verbs
    verbs = [word for word, pos in pos_tags if pos.startswith('V')]

    # Get synonyms for each verb
    for verb in verbs:
        synonyms = get_synonyms(verb)
        print(f"Verb: {verb}")
        print(f"Synonyms: {', '.join(synonyms)}\n")

```


## Output:
![279591120-84888cb1-37d8-4f2c-a8f3-ae0a0de8aa68](https://github.com/Prasannalakshmiganesan/Experiment-6---Implementation-of-Semantic-Analysis/assets/118610231/542647e3-aa36-4106-bc38-ac874347bc33)

## Result:
Thus, we have successfully implemented a program for Natural Language Processing.
