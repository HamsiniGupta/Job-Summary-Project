#job application project
import numpy
import pandas
import nltk
from nltk.corpus import stopwords
nltk.download('stopwords')
from nltk.tokenize import word_tokenize,sent_tokenize
nltk.download('punkt')



user_input = input("Please copy and paste job description here: ")

            
def letters_and_digits(user_input):
    cleaned = []
    words = word_tokenize(user_input)
    for word in words:
        if word.isalnum():
            cleaned.append(word)
    return cleaned
    
def stopWords(cleaned):
    tokenWords = []
    stop_words = set(stopwords.words("english"))
    for word in cleaned:
        if word not in stop_words:
            tokenWords.append(word)
    return tokenWords

            

cleaned_words = letters_and_digits(user_input)
print(cleaned_words)

x = stopWords(cleaned_words)
print(x)

temp = " ".join(x)

print(temp)


