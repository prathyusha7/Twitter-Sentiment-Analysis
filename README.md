Twitter-Sentiment-Analysis. 

To get started, run 

python twitterstream.py > output.txt 

python tweet_sentiment.py AFINN-111.txt output.txt 

APPROACH
Data in the form of raw tweets is acquired by using the python library “tweestream” which provides a package for simple twitter streaming API. This API allows two modes of accessing tweets: SampleStream and FilterStream. SampleStream simply delivers a small, random sample of all the tweets streaming at a real time. FilterStream delivers tweet which match a certain criterion.
AFINN is a list of English words rated for valence with an integer between minus five (negative) and plus five (positive). The words have been manually labeled by Finn Årup Nielsen in 2009-2011. The file is tab-separated. There are two versions: AFINN-111: Newest version with 2477 words and phrases. AFINN-96: 1468 unique words and phrases on 1480 lines. Note that there are 1480 lines, as some words are listed twice. The word list in not entirely in alphabetic ordering.
In sentiment analysis domain, the texts belong to either of positive or negative classes. There may also be multi-valued or binary classes like positive, negative and neutral (or irrelevant).
A. Lexical analysis
This technique is governed by the use of a dictionary consisting pre-tagged lexicons. The input text is converted to tokens by the Tokenizer. Every new token encountered is then matched for the lexicon in the dictionary. If there is a positive match, the score is added to the total pool of score for the input text. For instance, if “dramatic” is a positive match in the dictionary then the total score of the text is incremented. Otherwise the score is decremented or the word is tagged as negative. Though this technique appears to be amateur in nature, its variants have proved to be worthy.
B. Steps followed
First Step: Data Collecting – In this stage, data in the form of raw tweets is acquired by using the python library “tweestream” which provides a package for simple twitter streaming API.
Second Step: Pre-processing – In this stage, the acquired data is cleaned and made ready for feeding it into the classifier. Correcting the all uppercase and all lowercase to a common case, removing the non-English (or proffered language texts), removing un-necessary white spaces and tabs, etc. Here keywords are extracted using tokenization.
Third Step: Classification – This is the heart of the whole technique. Every new token encountered is then matched for the words in the AFINN.txt file. Here the score of each tweet is calculated depending on the words present in that particular tweet. The range thus calculated varies between negative and positive integers. If the score calculated for a tweet is negative integer, then this indicates that the sentiment of that tweet negative and the number indicates the amount of negativity. Same applies for the positive tweets. If the score of zero is obtained, then it indicates that the tweet is neutral.
