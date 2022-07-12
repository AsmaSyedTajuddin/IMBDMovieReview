# IMBDMovieReview
---------------------------
"""# Text Preprocessing"""

from tensorflow import keras
 from keras.preprocessing.text import Tokenizer

"""# What is Tokenizer ?
Text tokenization utility class.
This class allows to vectorize a text corpus, by turning each
text into either a sequence of integers (each integer being the index
of a token in a dictionary) or into a vector where the coefficient
for each token could be binary, based on word count, based on tf-idf...
"""

x = data["review"]
y = data["sentiment"]

y

tokenizer = Tokenizer(10000,lower=True)
tokenizer.fit_on_texts(x)
x[1]

sequence = tokenizer.texts_to_sequences(x)
sequence[1]
---------------------------------------

"""# Creating Custom review predictor bot"""

def imdb_bot(review):
  sentence_list = []
  sentence_list.append(review)
  sequence = tokenizer.texts_to_sequences(sentence_list)
  input = pad_sequences(sequence,maxlen=200,padding='pre')
  output = model.predict_classes(input)
  if output.all() == 1:
    print("The reviews are good you should watch this")
  else:
    print("The reviews are not quite good you should try another one")
-----------------------------------------------------------------
