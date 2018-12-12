# chat-based summarization
## tokenization - POS tagging
- filename --> pos_token/<dialogue number>.pickle (folder pos_token2 for new edition)
- format --> list of turn
- use Spacy
```
{
    'speaker': speaker,
    'turn': turn,
    'act': act,
    'text': tokens,
    'tags': tags,
    'pos':pos
}
```
 - speaker: Mr.One or Mr.Two (แปลงจาก A และ B เพราะมี Mr.A อยู่ใน dialogue)
 - turn: number of turn in dialogue
 - act: labled act of each turn
 - text: tokenized text of each turn
 - pos: POS tags from Spacy
  - [meaning of tag](https://cs.nyu.edu/grishman/jet/guide/PennPOS.html)
 - tag: dependency tag from Spacy

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