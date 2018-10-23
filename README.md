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