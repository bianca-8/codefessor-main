# Code Buddy - AI Detection Interview System

A web application that conducts AI-powered interviews to assess whether submitted code was written by a human or AI. Uses the Ribbon API to create personalized code review interviews.

[![Youtube Video: https://www.youtube.com/watch?v=buEkpqzZahM](https://img.youtube.com/vi/buEkpqzZahM/0.jpg)](https://www.youtube.com/watch?v=buEkpqzZahM)

## Features

- **Code Submission**: Students can paste their code and provide basic information
- **Automated Interview Generation**: Creates personalized interview questions based on the submitted code
- **AI-Powered Interviews**: Uses Ribbon's voice agent to conduct the interview
- **AI Detection Analysis**: Analyzes interview responses to determine likelihood of AI-generated code
- **Real-time Status Updates**: Tracks interview progress and provides real-time feedback
- **Detailed Results**: Provides scoring, confidence levels, and reasoning for the assessment

## How It Works

### 1. Code Submission
- Students enter their name, email, programming language, and paste their code
- The system generates appropriate interview questions based on the code and language

### 2. Interview Creation
- Creates a Ribbon interview flow with customized questions
- Generates a unique interview link for the student
- Questions focus on code understanding, implementation details, and problem-solving process

### 3. Interview Process
- Students click the provided link to start the AI-powered voice interview
- The Ribbon AI agent asks questions about the code
- Students explain their code, discuss their approach, and demonstrate understanding

### 4. Analysis & Scoring
- Once completed, the system analyzes the interview transcript
- Uses multiple factors to determine AI likelihood:
  - **Positive indicators** (human-written): Personal authorship claims, mentions of debugging, technical terminology usage
  - **Negative indicators** (AI-generated): Mentions of AI tools, uncertainty about code details, very brief responses
- Provides a score from 0-100 and confidence level

### 5. Results
- Displays detailed analysis including:
  - AI detection score and confidence level
  - Assessment of whether code is likely human or AI-generated
  - Reasoning behind the score
  - Full interview transcript

## Scoring Algorithm

The AI detection algorithm considers multiple factors:

### Positive Indicators (Human-written)
- **Personal Authorship** (+15): Uses phrases like "I wrote", "I coded", "I implemented"
- **Challenges Mentioned** (+10): Discusses struggles, difficulties, or challenges
- **Debugging Process** (+12): Mentions debugging, fixing bugs, or errors
- **Technical Terminology** (+10): Uses relevant programming concepts and terminology

### Negative Indicators (AI-generated)
- **AI Tool Mentions** (-25): References ChatGPT, AI, or generation tools
- **Copy/Paste References** (-15): Mentions copying or pasting code
- **Uncertainty** (-12): Shows lack of understanding with "don't know" or "can't explain"
- **Brief Responses** (-10): Very short or generic responses

### Score Interpretation
- **70-100**: Likely human-written (high confidence if 80+)
- **50-69**: Possibly human-written (medium confidence)
- **30-49**: Possibly AI-generated (medium confidence)
- **0-29**: Likely AI-generated (high confidence if <20)

## Supported Programming Languages

- JavaScript
- Python
- Java
- C++
- C
- C#
- Go
- Rust
- PHP
- Ruby
- Swift
- Kotlin
- Other (custom questions)

## Customization

### Adding New Languages
Edit the `generateCodeQuestions` function in `server.js` to add language-specific questions.

### Modifying Scoring Algorithm
Update the `analyzeForAIDetection` function in `server.js` to adjust scoring factors and weights.

### Interview Questions
Customize the base questions in the `generateCodeQuestions` function to focus on different aspects of code understanding.

## License

This project is for educational purposes. Please ensure compliance with Ribbon AI's terms of service.
