# chat-based summarization
## tokenization - POS tagging
- filename --> pos_token/<dialogue number>.pickle
- format --> list of turn
```
{
	'speaker': speaker,
	'turn': turn,
	'act': act,
	'text': text,
	'tags': tags
}

```
 - speaker: A or B
 - turn: number of turn in dialogue
 - act: labled act of each turn
 - text: tokenized text of each turn
 - tags: POS tags of the turn from nltk
  - meaning of tag 
  https://medium.com/@gianpaul.r/tokenization-and-parts-of-speech-pos-tagging-in-pythons-nltk-library-2d30f70af13b


Brief example for dialogues 1
```
[
	{
		'act': 'directive',
		'speaker': 'A',
		'tags': [('So', 'RB'), ('Dick', 'NNP'), (',', ','),('how', 'WRB'), ('about', 'IN'),('getting', 'VBG'),('some', 'DT'), ('coffee', 'NN'),('for', 'IN'),('tonight', 'NN'), ('?', '.')],
		'text': ['So','Dick',',','how','about','getting','some','coffee','for','tonight','?'],
		'turn': 1
	},
 	{
		'act': 'commissive',
  		'speaker': 'B',
  		'tags': [('Coffee', 'NN'),('?', '.'),('I', 'PRP'),('don', 'VBP'),('’', 'JJ'),('t', 'NN'),('honestly', 'RB'),('like', 'IN'),('that', 'DT'),('kind', 'NN'),('of', 'IN'),('stuff', 'NN'),('.', '.')],
		'text': ['Coffee','?','I','don','’','t','honestly','like','that','kind','of','stuff','.'],
		'turn': 2
	},
	..........
]
```