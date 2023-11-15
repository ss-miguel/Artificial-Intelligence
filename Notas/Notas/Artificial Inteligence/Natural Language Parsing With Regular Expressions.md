## Introduction
Discovering new [[code words]] in declassified CIA documents may seem like a mission for a foreign intelligence service, and detecting [[gender biases]] in the Harry Potter novels a task for a literature professor. Yet by utilizing [[natural language parsing]] with [[regular expressions]], the power to perform such analyses is in your own hands!
While you may not put much explicit thought into the structure of your sentences as you write, the syntax choices you make are critical in ensuring your writing has [[meaning]]. Analyzing such [[sentence structure]] as well as [[word choice]] can not only provide [[insights]] into the [[connotation]] of a piece of text but can also [[highlight]] the [[biases]] of its author or [[uncover additional insights]] that even a deep, rigorous reading of the text might not reveal.
By using [[Python]]’s [[regular expression module]] and the [[Natural Language Toolkit]], known as [[NLTK]], you can find [[keywords]] of interest, discover where and how often they are used, and discern the [[parts-of-speech patterns]] in which they appear to understand the sometimes [[hidden meaning]] in a piece of writing.
```
from nltk import RegexpParser
from pos_tagged_oz import pos_tagged_oz
from np_chunk_counter import np_chunk_counter

# define noun-phrase chunk grammar here
chunk_grammar = "NP: {<DT>?<JJ>*<NN>}"

# create RegexpParser object here
chunk_parser = RegexpParser(chunk_grammar)

# create a list to hold noun-phrase chunked sentences
np_chunked_oz = list()

# create a for-loop through each pos-tagged sentence in pos_tagged_oz here
for pos_tagged_sentence in pos_tagged_oz:
	# chunk each sentence and append to np_chunked_oz here
	np_chunked_oz.append(chunk_parser.parse(pos_tagged_sentence))

# store and print the most common np-chunks here
most_common_np_chunks = np_chunk_counter(np_chunked_oz)
print(most_common_np_chunks)
```
