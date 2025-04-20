#---------Question1---------------#
Take a dataset form the dakshina_dataset_v10.0.tar  which contain text data in form of Latin-to-Devanagari transliterations.
The dataset is extracted from the Dakshina dataset and consists of Latin text and Devanagari text
A vocabulary is built for both the Latin and Devanagari text, including special tokens for the start(\t) and end (\n) of the sequence for the target language.
The Latin and Devanagari text is transformed into numerical sequence,where each character is mapped to a unique token index.The padding is applied.
The model consists of an encoder and a decoder, both built using LSTm or GRU .
The encoder processes the input Latin text and encodes it into a set of hidden states.
The decoder uses these hidden states to generate the corresponding Devanagari translation,one character at a time.
The model is trained using the Adam optimizer and categorical cross-entropy loss, and its performance is tracked using the validation set.
During inference, the trained model is used to predict Davanagari translations for new Latin words, generating one character at a time until the end token is predicted.
The model is evaluated on a test set, and accuracy is calculated by comparing predicted Devanagari translations with the actual labels.
#---------Question2---------------#
A ZIP achive is extracted containing lyric files.
GPT-2 and its tokenizer are loaded from Hugging face Transformers.
Each lyric is tokenized into a fixed-length input with padding and truncation.
The text is removed from the dataset after tokenization, leaving only input_ids and attention_mask.
A custom trainer is initialized with a data collactor function,ensuring proper tensor formatting.
After training,both the model and tokenizer are saved to a specified directory.
A function generate_lyrics() is used to load a fine-tuned model and tokenizer,Generate new lyrics using a given prompt with sampling.
A prompt is passed to the model. The model returns several stylistically relevant completions of lyrics.
