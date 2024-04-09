# self-attention-network-sentiment-classification
I try to implement Self-Attention network for sentiment classification. This is equivalent to a Single Head of a Multi Head Transformer Encoder. 

## Visualization for a Negative Sentiment
**Input text:** 'Horrible acting with the worst special f/x I\'ve ever bore witness too. It\'s bad enough I wasted $3 to watch this crummy pile of crap, but it\'s the hour and a half time I lost that I could\'ve been doing anything else like getting a root canal or volunteering for jury duty. Getting drunk couldn\'t even help this video.<br /><br />To put it bluntly, I sincerely believe I actually lost a few IQ points during the course of watching this idiotic piece of mind-numbing "work"! Perhaps I should have followed my own advice this time. Never expect a decent film if it\'s written, directed and produced by the same person, and never EVER expect anything of value from Jeff Fahey.'

The input text is preprocessed and then sent to Self-Attention network for classification.

### Attention Visualization
![Alt-Text](https://github.com/MonojitSarkar/self-attention-network-sentiment-classification/blob/main/images/negative_1.png)

### Interpretation: 
Look at the words highlighted in red. Those are the words which the network pays most attention to classify the input as negative. The next important words are highlighted in brown and black.

## Visualization for a Positive Sentiment
**Input text:** 'I used to have a fascination with the cartoon back in college when it was being made. It had much the charm of "Get Smart". While it admittedly had its faults, it was rather enjoyable.<br /><br />Naturally I was very interested in seeing the film version. That was before I saw it. Afterwords I wished it had never been made.<br /><br />Besides being miscast all around (who on Earth though Broderick was even close to the role?) it just didn\'t make the grade.<br /><br />The effects were reasonable and perhaps the ONLY thing I liked about the movie; seeing a live-action version of the gadgets in action! What was missing was a story and treatment which made it funny or charming or interesting.<br /><br />The original was a wacky cartoon with a very lighthearted attitude. It was FUN. The motion picture became murky and took itself FAR too seriously. If it had seriously had a great plot or went crazy enough to make it seem like a "cartoon on film" it might have been enjoyable.<br /><br />As it exists it doesn\'t deserve to be considered part of the "Gadget Legacy".'

The input text is preprocessed and then sent to Self-Attention network for classification.


### Attention Visualization
![alt text](https://github.com/MonojitSarkar/self-attention-network-sentiment-classification/blob/main/images/positive_2.png)

### Interpretation: 
Look at the word highlighted in red. Those are the words which the self-attention network most importance to for positive classification. 
Notice the words highlighted in brown and black. They are also deemed important but less than those words in red. 

## To-Do
- [ ] Implement Word Embedding and see for any improvement
- [ ] Better word preprocessing.

## References
- @article{DBLP:journals/corr/abs-1812-07860,
  author       = {Artaches Ambartsoumian and
                  Fred Popowich},
  title        = {Self-Attention: {A} Better Building Block for Sentiment Analysis Neural
                  Network Classifiers},
  journal      = {CoRR},
  volume       = {abs/1812.07860},
  year         = {2018},
  url          = {http://arxiv.org/abs/1812.07860},
  eprinttype    = {arXiv},
  eprint       = {1812.07860},
  timestamp    = {Wed, 02 Jan 2019 14:40:18 +0100},
  biburl       = {https://dblp.org/rec/journals/corr/abs-1812-07860.bib},
  bibsource    = {dblp computer science bibliography, https://dblp.org}
}
