# Resume-Selector

Dataset Description: The data was downloaded from the website kaggle. The data is in Excel format, with the three column ID, Category, and Resume.
ID: The sequence number of the resume
Category: Industry sector to which the resume belongs to
Resume: The complete CV of the candidate.


A.Pre-Processing
The resume provided as input is included in the final list of this procedure to remove special or unnecessary characters from the resume. words of all unique letters, numbers and single letters are removed during cleanup. After these processes, we had a clean data set with no unique letters, numbers, or single letter words. The NLTK tokenizer is used to partition the dataset into tokens. Stopword removal, heading , and vectorization are among the preprocessing operations performed on the markup data set. Data is masked in the following way:


Masking the string such as \w
Masking the escape letters like \n
Masking all the numbers
Replace all the single letter words with an empty string
Mask email addresses
Stop words are removed
Lemmatization is performed
Removing Stop Words: Stopwords like and,the,was etc. are very common in words and are removed as they limit the process of determining predictions.
Stopword filtering consists of the following:

The input words are tokenized into individual tokens and saved in an array.

Each word now corresponds to the Stop Words list in the NLTK library:
import stopwords from nltk.corpus
SW[] = set(stopwords.words('english'))
It returns 180 stop words, which may be confirmed using the (len(StopWords)) function and displayed using the print(StopWords) function.

When the words appear in the StopWords list, they are removed from the main sentence array.

Repeat the above sequence of steps until the tokenized array's last entry is not matched.

There are no stop words in the resultant array


The next step is feature extraction. TfIdf was used to extract features from the preprocessed data set. The cleaned data was passed in and the function was extracted using TfIdf. Taking the input as a vector of numbers, the classification model is processed based on machine learning or a learning algorithm. The variable-length input text was not processed by the
ML-based classifier. Accordingly, in the preparation process, the text is changed to an essential vector form of the same length There are several methods for extracting
characteristics, including tf-idf, and others. Using the scikit learn library function, we generated tf-idf for each term.
To calculate a tf-idf vector,we use TfidfVectorizer:
Sub-linear df is set to True to utilise a logarithmic form for frequency.
Min df is the minimal number of documents in which a word must appear in order to be saved.
The norm is set to l2 to ensure that all feature vectors have the same euclidean norm.
The gramme range is set to (n1, n2), with n1 equaling 1 and n2 equaling 2. It means that both unigrams and bigrams are taken into account.
