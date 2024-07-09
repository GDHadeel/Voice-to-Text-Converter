# Voice-to-Text-Converter

# Task 4: Building a User Interface for Voice-to-Text Conversion

## Description
This project is a web-based application that allows users to convert spoken language into written text and store it in a MySQL database. This project provides a simple yet effective way to capture spoken input and save it for further use or analysis.

https://github.com/GDHadeel/Voice-to-Text-Converter/assets/126657301/44e70678-59cd-40d4-a4f6-0deaea9e8150

---

## Installation and Setup

1. **Database Setup:**

   - Create a MySQL database named `robot`:
     ```sql
     CREATE DATABASE robot;
     USE robot;
     ```
   - Create a table named `transcript` within the `robot` database:
     ```sql
     CREATE TABLE transcript (
         id INT AUTO_INCREMENT PRIMARY KEY,
         text TEXT NOT NULL,
         created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
     );
     ```

2. **Web Interface Setup:**

   - Place [`index.html`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/index.html) and [`save_text.php`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/save_text.php) in your web server's directory.

3. **Configuration:**

   - Edit [`save_text.php`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/save_text.php) to configure your MySQL database connection parameters (`$servername`, `$username`, `$password`, `$dbname`).

## Usage

1. Open [`index.html`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/index.html in a supported web browser.
2. Click the "Start Recording" button to initiate speech recognition.
3. Speak into your microphone clearly and audibly.
4. The transcribed text will appear in the display area and be saved automatically to the `transcript` table in the `robot` database.

## Code Explanation

### HTML ([`index.html`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/index.html)
- Provides the structure and content for a webpage titled "Voice to Text Converter".
- Includes a button (`#start-btn`) to initiate speech recognition and a paragraph (`#result`) to display the recognized text.

### CSS
- Defines styles for the webpage, including background image, container layout, button appearance (`#start-btn`), and result text (`#result`).

### JavaScript
- Implements speech recognition using the `SpeechRecognition` API.
- Handles user interaction by starting and stopping recognition upon button click (`#start-btn`).
- Sends recognized text to `saveTextToDatabase` function for database storage using XMLHttpRequest.

### PHP ([`save_text.php`](https://github.com/GDHadeel/Voice-to-Text-Converter/blob/main/save_text.php))
- Receives POST requests with a transcript parameter.
- Establishes a connection to a MySQL database (`robot`) on localhost.
- Sanitizes and inserts transcript data into the `transcript` table.
- Provides error handling for database connection and insertion operations.

## Acknowledgments
https://medium.com/@gopesh3652/building-a-voice-to-text-app-with-javascript-a-step-by-step-guide-9042493bdd63
