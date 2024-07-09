# Voice-to-Text-Converter

# Task 4: Building a User Interface for Voice-to-Text Conversion

## Description
This project is a web-based application that allows users to convert spoken language into written text and store it in a MySQL database. This project provides a simple yet effective way to capture spoken input and save it for further use or analysis.

https://github.com/GDHadeel/Voice-to-Text-Converter/assets/126657301/44e70678-59cd-40d4-a4f6-0deaea9e8150

---

## Features

- **Speech Recognition:** Utilizes the browser's SpeechRecognition API to transcribe spoken words into text.
- **Database Integration:** Saves the transcribed text along with timestamped metadata into a MySQL database.
- **User Interface:** Provides a simple web interface (`voiceToText.html`) with a button to start recording and a display area for transcribed text.
- **Error Handling:** Includes basic error handling for database connectivity and speech recognition failures.

## Prerequisites

To set up and run Voice to Text Converter, ensure you have the following:

- **MySQL Database:** Set up a MySQL server instance. You'll need to create a database named `robot` and a table named `transcript`.
- **Web Server:** A server environment (e.g., Apache, Nginx) with PHP support.
- **Supported Browser:** Ensure your browser supports the SpeechRecognition API (e.g., Google Chrome, Mozilla Firefox).

## Installation and Setup

1. **Database Setup:**

   - Create a MySQL database named `robot`:
     ```sql
     CREATE DATABASE robot;
     USE robot;
     ```
   - Create a table named `transcripts` within the `robot` database:
     ```sql
     CREATE TABLE transcripts (
         id INT AUTO_INCREMENT PRIMARY KEY,
         text TEXT NOT NULL,
         created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
     );
     ```

2. **Web Interface Setup:**

   - Place `voiceToText.html` and `voiceToText.php` in your web server's directory.

3. **Configuration:**

   - Edit `voiceToText.php` to configure your MySQL database connection parameters (`$servername`, `$username`, `$password`, `$dbname`).

## Usage

1. Open `index.html` in a supported web browser.
2. Click the "Start Recording" button to initiate speech recognition.
3. Speak into your microphone clearly and audibly.
4. The transcribed text will appear in the display area and be saved automatically to the `transcripts` table in the `robot` database.

## Code Explanation

### HTML (voiceToText.html)

- Structures the web page with a button to start voice input and a `<div>` to display the transcribed text.

### CSS

- Styles the page with a light pink background, styled buttons, and a message box.

### JavaScript

- Uses the Web Speech API to convert speech to text.
- Sends the transcribed text to the server using an AJAX request.

### PHP (voiceToText.php)

- Handles server-side processing.
- Inserts the transcribed text into the `transcripts` table in the `robot` database.

## Acknowledgments

https://medium.com/@gopesh3652/building-a-voice-to-text-app-with-javascript-a-step-by-step-guide-9042493bdd63
