# chat-based summarization
## tokenization - POS tagging
- filename --> pos_token/<dialogue number>.pickle (folder pos_token2 for new edition)
- format --> list of turn
- use Spacy
- เพิ่มการแปลงสรรพนาม you, i และเปลี่ยนกริยาของมันให้เป็นกริยาเอกพจน์
- แปลง 'll เป็น will และ n't เป็น not
  - 'd ยังเป็นปัญหาเนื่องจากไม่ทราบว่าเป็น would หรือ had
- วิธีการคร่าวๆ
    - ยัดเข้าไปทั้ง dialogue จัดการหา coreference แทนอันที่ไม่เป็น pronoun แทน pronoun
    - ยัดทีละ turn แปลง pronoun (กรณีสรรพนามบุรุษที่ 1 และ 2) และ verb (กรณีแปลง pronoun)
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
  - [meaning of pos tag](https://cs.nyu.edu/grishman/jet/guide/PennPOS.html)
 - tag: [dependency tag from Spacy](https://nlp.stanford.edu/software/dependencies_manual.pdf)

Brief example for dialogues 1
```
[
    {
        'speaker': 'Mr.One', 
        'turn': 1, 
        'act': 'directive', 
        'text': ['So', 'None', ',', 'how', 'about', 'getting', 'some', 'coffee', 'for', 'tonight', '?'], 
        'tags': ['RB', 'NN', ',', 'WRB', 'IN', 'VBG', 'DT', 'NN', 'IN', 'NN', '.'], 
        'pos': ['ADV', 'NOUN', 'PUNCT', 'ADV', 'ADP', 'VERB', 'DET', 'NOUN', 'ADP', 'NOUN', 'PUNCT']
    }, 
    
    {
        'speaker': 'Mr.Two', 'turn': 2, 'act': 'commissive', 
        'text': ['Coffee', '?', 'Mr', '.', 'Two', 'does', 'not', 'honestly', 'like', 'that', 'kind', 'of', 'stuff', '.'], 
        'tags': ['NN', '.', 'NNP', '.', 'CD', 'VBZ', 'RB', 'RB', 'VB', 'DT', 'NN', 'IN', 'NN', '.'], 
        'pos': ['NOUN', 'PUNCT', 'PROPN', 'PUNCT', 'NUM', 'VERB', 'ADV', 'ADV', 'VERB', 'DET', 'NOUN', 'ADP', 'NOUN', 'PUNCT']
    }, 
    .....
]
```