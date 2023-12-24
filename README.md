Goal of MMR (Multi-modal music recognizer) is to recognize songs as input which users do not know the song name but they know either melody, lyrics, or both. This will help them buying songs from music platform such as Apple Music, Amazon Music, etc. I am aware that today we have Shazam. Although the quality of Shazam is good, we have some problems in a certain situations. 1.The quality of output is not accurate when there exists noise in the background.

2.A song input is Remix, so original music features are changed such as tempo, singer, frequency, amplitude and time. If remix is not registered in the databse, ot becomes hard to find a song name. => There exists a solution even from a remix because remix is the result of changing tempo, amplitude, adding additional audio on top of original song, etc.

Here are steps we can take:

1. Extract Audio Features Step 1: Preprocess Audio Data

Objective: Convert audio files into a standardized format (e.g., WAV) for consistent analysis. Tools: Use audio processing libraries like Librosa or PyDub in Python. Step 2: Feature Extraction

Objective: Extract key audio features such as melody, tempo, intensity, harmony, voice, and instruments. Tools: Utilize Librosa for extracting features like tempo, intensity, and harmony. For melody and voice, consider using more advanced models like CREPE for pitch tracking or OpenL3 for audio embedding.

2. Search from Database by These Features Step 3: Database Construction

Objective: Build a database of songs with pre-extracted features. Tools: Use a database management system (e.g., SQL, MongoDB) and store feature vectors extracted in Step 2. Step 4: Feature Matching

Objective: Implement a search algorithm to find matches based on audio features. Tools: Use similarity measures (e.g., cosine similarity, Euclidean distance) in Python to compare feature vectors.

3. Rank Candidates in Order Step 5: Implement Ranking Algorithm Objective: Rank potential matches based on similarity scores and other relevant metrics. Tools: Develop a ranking algorithm (possibly using machine learning) to weigh different features appropriately.

4. Propose Candidates of Song Name and Artist Step 6: Integration with GPT Models

Objective: Use GPT models to refine search results and generate more contextual and accurate suggestions. Tools: Employ a GPT model like GPT-4 to process textual information about songs (like lyrics, artist info) to enhance matching accuracy. Step 7: User Interface and Feedback Loop

Objective: Present candidates to users and refine the system based on feedback. Tools: Create a user interface (web or mobile app) and implement a feedback system to continuously improve the algorithm based on user input. Step 8: Continuous Learning and Improvement

Objective: Keep updating the database and refining the model with new data and user feedback. Tools: Use automated scripts to update the database and retrain models periodically.
