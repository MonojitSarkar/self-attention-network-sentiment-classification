# self-attention-network-sentiment-classification
I try to implement Self-Attention network for sentiment classification. This is equivalent to a Single Head of a Multi Head Transformer Encoder. This is the implementation of the paper in the reference.

## Architecture
![alt-text](https://github.com/MonojitSarkar/self-attention-network-sentiment-classification/blob/main/images/ssan_model.png)

Accuracies for different embedding trained for 20 epochs. Dropout of 0.7

| Architecture Type  | Train Accurcy | Test Accuracy |
| ------------- | ------------- | ------------- |
| LSTM Random Word Embedding (no dropout) | 94.10% | 84.88% |
| LSTM Random Word Embedding (dropout in lstm cell) | 95.84% | 83.77% |
| LSTM Random Word Embedding | 78.60% | 73.80% |
| LSTM Glove 6B 50 dim | 60.81% | 64.16% |
| LSTM Glove 6B 100 dim | 61.22% | 57.66% |
| BiLSTM Glove 6B 50 dim | 76.72% | 81.72% |
| BiLSTM Glove 6B 100 dim | 80.90% | 80.82% |
| Self-attention Random Word Embedding | 81.00%  | 82.44% |
| Self attention Glove 6B 50 dim  | 84.77%  | 82.35% |
| Self attention Glove 6B 100 dim  | 85.31%  | 84.27% |

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
- [x] Implement Glove and see for any improvement. Slightly better accuracy observed.
- [x] Implement Glove embeddings with different dimensions.
- [ ] Better word preprocessing.
- [ ] Implement Relative Positional Encoding
- [x] See how LSTM performs

## References
- @inproceedings{Ambartsoumian2017, <br />
  author    = {Ambartsoumian, Artaches and Popowich, Fred}, <br />
  title     = {Self-Attention: A Better Building Block for Sentiment Analysis Neural Network Classifiers},<br />
  booktitle = {Proceedings of the 9th Workshop on Computational Approaches to Subjectivity, Sentiment and Social Media Analysis},<br />
  month     = {November},<br />
  year      = {2018},<br />
  address   = {Brussels, Belgium},<br />
  publisher = {Association for Computational Linguistics},<br />
}
