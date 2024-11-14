# Project: 
- TAMU Datathon first place winner Connections AI model.
- Grouper for solving New York Times Connections using contextual and semantic similarity.
- Flask Application for Category Detection and Word Puzzle Solving

# Description: 
- Developed a Flask API that leverages OpenAI and spaCy NLP to process word sets, identify matching categories, and suggest solutions for word puzzles based on semantic similarity and word play. The application enables high-performance matching and word prediction through caching and optimized vector operations.
- Also checks for possible anagrams, palindromes and word puzzle similarity.

# Key Features:

- Category Matching: Matches user-submitted words to pre-defined categories, using exact matching, semantic similarity, and heuristics.
- Word Prediction: Utilizes cosine similarity on word vectors to predict missing words in a set and suggest potential category memberships.
- OpenAI Integration: Employs OpenAI's GPT model for advanced word puzzle hints, especially for anagram and semantic challenges.
- Data Processing: Reads category data from JSON files, standardizes word format, and uses word vectors to compute contextual similarities.
- Performance Optimization: Implements caching with lru_cache to reduce repetitive processing and improve response times for frequently used NLP operations.
- Error Handling & Logging: Includes robust error logging for data loading and API errors, ensuring reliable performance.
- Ensures the same answer isn't returned twice on the rare occasion of an incorrect guess. 
- Given 3 words and "One Away" hint, the fourth word is predicted using semantic similarity. If less than 3 words are correct it falls back to GPT4o, and if it is still incorrect it falls back to a third model.

# Technologies Used:

- Backend: Python, Flask, spaCy (en_core_web_md model), OpenAI API, NumPy
- API: JSON-based RESTful endpoints for client interaction
- Utilities: Logging for performance monitoring and troubleshooting

# Example inputs and outputs:
- A list of remaining words, correct guesses, incorrect guesses and whether the previous guess was OneAway from the true answer is passed to the API.
- The API is designed to return a list of four elements as the next best guess. The reason for designing this project using an API is because the datasets were large and we wanted to mask our API keys.

# Usage:
- Clone the repository and run apilauncher.py in order to start the API. Pass in command line arguments for the correct dataset and expanded dataset using python apilauncher.py <datasetjson1> <datasetjson2>
- 2 example datasets have been provided containing categories used in previous games and an expanded data set to predict future games.
- Ensure that app.py has the correct ip address given present in the function calling the API.
- Run app.py and then run evaluator.py to evaluate the default test cases.
- Other hidden randomized test cases were passed into the function to conclude the winner.
