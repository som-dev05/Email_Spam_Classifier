# Catching Spam Like a Pro: Email & SMS Classifier

Hey there! Welcome to my spam classifier project. 

Let's be real—nobody likes waking up to text messages saying they've just won a lottery they never entered, or emails claiming their bank account is locked. I wanted to tackle this classic Natural Language Processing (NLP) problem hands-on to see exactly how machines learn to filter out the junk. 

Whether you're a first-year student just getting your feet wet with Python or a seasoned developer looking for a clean NLP pipeline, I hope you find this repo helpful!

## The "Why" Behind the Code

In spam detection, the absolute worst-case scenario is a **false positive**—imagine an important email from a professor or a recruiter getting sent straight to the spam folder. Because of that, my main goal wasn't just to get high accuracy; I wanted to absolutely maximize **Precision**. 

I fired up my Pop!_OS setup, grabbed a dataset, and put a few Naive Bayes algorithms head-to-head to see which one could be trusted to never misclassify a legitimate message.

## The Toolkit

Here is what I used to build this:
* **Python** (The backbone)
* **Pandas & NumPy** (For data wrangling)
* **Matplotlib & Seaborn** (For plotting cool charts and heatmaps)
* **NLTK** (To break down the text, remove stop words, and stem the words down to their roots)
* **Scikit-Learn** (For the machine learning magic: TF-IDF and Naive Bayes)

## How It Works (The Process)

1. **Cleaning House:** First, I scrubbed the dataset, removed duplicates to stop data leakage, and mapped our targets (0 for normal "Ham", 1 for "Spam").
2. **Exploring the Data (EDA):** I dug into the dataset and found it was super imbalanced (about 87% normal messages and 13% spam). I also noticed spam messages tend to be way longer and use a lot more characters.
3. **Text Preprocessing:** I built a custom pipeline to convert everything to lowercase, strip out punctuation and useless stop words, and apply stemming.
4. **Vectorization:** Computers can't read words, so I used `TfidfVectorizer` (capped at 3000 features) to turn those words into numbers.

## The Winner

I tested three different models. Here is how they stacked up:

* **Gaussian Naive Bayes:** 86.36% Accuracy | 46.60% Precision (Yikes, too many false positives)
* **Bernoulli Naive Bayes:** 97.38% Accuracy | 98.05% Precision (Really good, but not perfect)
* **Multinomial Naive Bayes:** **96.71% Accuracy | 100% Precision**

By pairing the Multinomial model with TF-IDF, it hit a flawless 100% precision score. It might miss a tiny fraction of spam, but it will **never** throw a real message into the trash.

## Wanna try it out?

Feel free to fork this and play around with it on your own machine!
