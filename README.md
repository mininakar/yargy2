# yargy2
This is a yargy library, but now it interacts well with <b>pymorphy3</b>.

# Install
<pre>
<code>
pip install yargy2
</code>
</pre>

# Usage
```python
    from yargy2 import Parser, rule, or_
    from yargy2.predicates import in_
    positive_word_list = load_word_list(positive_file_path)

    negative_word_list = load_word_list(negative_file_path)

    positive_rule = or_(
                rule(in_(positive_word_list)))

    negative_rule = or_(
                rule(in_(negative_word_list)))

    positive_parser = Parser(positive_rule)
    negative_parser = Parser(negative_rule)

     positive_count = 0
     negative_count = 0

      for word in line.split():
            if word.lower() in positive_word_list:
                   positive_count += 1
            elif word.lower() in negative_word_list:
                  negative_count += 1
      total_words = len(line.split())

      positive_words_count = len(list(positive_parser.findall(line)))
      negative_words_count = len(list(negative_parser.findall(line)))
```
