# QuizSpace — Java Quiz App with Web UI

A browser-based quiz dashboard powered by the original Java question bank and scoring logic. The UI uses HTML, CSS and JavaScript; a small Java HTTP server provides the API. No third-party Java libraries or Node.js are required.

## Requirements
- JDK 17 or newer
- Windows, macOS or Linux
- A browser (Chrome, Edge, Firefox, etc.)

## Run on Windows
1. Extract the complete `QuizApp` folder from the ZIP.
2. Open the extracted folder. Make sure `src`, `web`, `questions.csv`, and `run.bat` are directly inside it.
3. Double-click `run.bat`.
4. Wait until the terminal says `QuizApp UI is running at http://localhost:8081`.
5. Open Chrome or Edge and visit **http://localhost:8081**.
6. Keep the terminal window open while using the app. Press Ctrl+C in it when finished.

If Windows says the port is already in use, close another QuizApp window or change `8081` in `src/ApiServer.java`, then re-run `run.bat`.

## Run from VS Code terminal
Open the main `QuizApp` folder (not `src`) and use:

```powershell
javac -d out src\*.java
java -cp out ApiServer
```

Then visit http://localhost:8081. Stop the server with Ctrl+C.

## Features
- Dashboard with answer totals, accuracy, categories and topic performance
- Mixed quiz or category-specific quizzes
- 30-second timer per question and progress bar
- Results summary and topic breakdown
- Answer review showing your answer and the correct answer
- Retake the same category or start a different one
- Persistent topic stats in `stats.csv`
- Persistent quiz history in `history.csv`
- Existing `questions.csv` question bank remains the source of quiz questions

## Add questions
Edit `questions.csv`, preserving the header and format:

```csv
topic,question,answer
Java,What keyword makes a variable constant?,final
```

Avoid commas inside question text or answers because this starter project uses a simple CSV parser. Restart the app after editing questions.

## Files
- `src/Question.java` — question model and answer checking
- `src/QuestionBank.java` — loads questions and categories
- `src/QuizSession.java` — original console quiz session (retained)
- `src/ScoreTracker.java` / `src/TopicStats.java` — persistent topic accuracy
- `src/ApiServer.java` — Java HTTP API and static-file server
- `web/index.html` — page layout
- `web/style.css` — responsive styling
- `web/app.js` — UI behavior and API calls
