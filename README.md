# AI Sentiment Analyzer – Feature Set B

## Problem Statement
Develop an AI Sentiment Analyzer that accepts a user's review as input, analyzes the review, classifies its sentiment, calculates a sentiment score, and displays the result clearly.

## Feature Set B
1. **Review Input** – large text box, "Analyze Sentiment" button, "Clear" button.
2. **Sentiment Classification** – Positive, Negative or Neutral.
3. **Sentiment Score** – numerical score from -1.00 to +1.00.
4. **Display Result** – entered review, classification, score and a short explanation.

## Technologies Used
- Python 3 (standard library only)
- Tkinter (desktop GUI, included with Python)

No external libraries, datasets, databases or internet connection are required.

## Python Version
Python 3.8 or higher.

## Features
- Clean desktop interface built with Tkinter
- Dictionary-based sentiment analysis (no machine-learning libraries)
- Handles punctuation and mixed upper/lower case
- Simple negation handling ("not good" counts as negative, "not bad" as positive)
- Safe handling of empty input ("Please enter a review.")
- Colour-coded result and a plain-English explanation
- One-click example reviews

## How the Sentiment Analyzer Works
1. **Clean** – convert the review to lowercase and remove punctuation.
2. **Split** – break the review into individual words.
3. **Count** – compare every word with the built-in positive and negative word lists. If a negation word (e.g. *not*, *never*, *don't*) appears in the two words before a sentiment word, its meaning is flipped.
4. **Score** – calculate

   `score = (positive − negative) / (positive + negative + 1)`

   The result always lies between -1.00 and +1.00. If no sentiment words are found, the score is 0.
5. **Classify**

   | Score | Sentiment |
   |-------|-----------|
   | greater than 0.10 | Positive |
   | less than -0.10 | Negative |
   | otherwise | Neutral |

6. **Explain** – list the words that were found and why the review received its label.

## How to Run the Project
1. Install Python 3 from https://www.python.org (tick "Add Python to PATH" on Windows). Tkinter is included. On some Linux systems install it with `sudo apt install python3-tk`.
2. Download or clone this folder.
3. Open a terminal / command prompt inside the `AI_Sentiment_Analyzer` folder.
4. Run:

```
python main.py
```
(On Linux/macOS you may need `python3 main.py`.)

## Project Structure
```
AI_Sentiment_Analyzer/
├── main.py                 # Tkinter GUI (entry point)
├── sentiment_analyzer.py   # Sentiment analysis logic
├── README.md
└── sample_reviews.txt
```

## Sample Inputs and Expected Outputs
| Input Review | Sentiment | Score |
|--------------|-----------|-------|
| I really loved this product. It is excellent and amazing. | Positive | +0.75 |
| The product is terrible and disappointing. | Negative | -0.67 |
| The product is okay. | Neutral | 0.00 |
| This is not good. | Negative | -0.50 |
| Great quality, wonderful design, but a bit expensive. | Positive | +0.25 |
| Good product but slow delivery. | Neutral | 0.00 |

## Future Scope
- Larger word lists or a downloadable lexicon
- Handling intensifiers ("very good") and emojis
- Loading reviews from a file and analyzing many reviews at once
- Charts showing sentiment over many reviews
- Machine-learning based model for higher accuracy
- Support for other languages
