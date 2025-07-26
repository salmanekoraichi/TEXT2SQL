
# Voice2SQL

A modern full-stack web application that converts voice input to natural language text and then transforms it into executable SQL queries. This application bridges the gap between verbal communication and database interaction, making data querying more accessible and intuitive.

## Introduction

Voice2SQL is designed for developers, data analysts, and business users who want to interact with databases using natural language rather than writing complex SQL queries manually. It's particularly useful for:

- Developers looking to integrate voice-based database querying into their applications
- Data analysts who want a quicker way to perform database operations
- Business users with limited SQL knowledge who need to access database information
- Accessibility applications where typing might be difficult or impossible
## Features

- Voice-to-text conversion using Web Speech API
- Natural language to SQL translation using OpenAI API
- MongoDB query generation and simulated execution
- Real-time feedback with streaming results
- Sample database with pre-populated data for testing
- Mobile-responsive interface with intuitive controls
- Query history for tracking past interactions
- Light/dark mode toggle for user preference

## Tech Stack

- **Frontend**: React, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express
- **APIs**: Web Speech API, OpenAI API
- **Database**: MongoDB (simulated for demo)

## Getting Started

### Prerequisites

- Node.js (v14 or later)
- npm or yarn
- **Gemini API key** (required for natural language to SQL conversion)
- MySQL server running locally with the required database schema

### Installation

1. Clone the repository:

```bash
git clone https://github.com/ProjectBadir/voice-2-sql.git
cd voice-2-sql
```

2. Install dependencies:

```bash
npm install
```

3. **Set up your Gemini API key:**

   a. Go to [Google AI Studio](https://aistudio.google.com/app/apikey) and create a new API key
   
   b. Create a `.env` file in the root directory and add your Gemini API key:

   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   PORT=3001
   ```

   **⚠️ Important:** Replace `your_gemini_api_key_here` with your actual Gemini API key.

4. **Set up MySQL Database:**

   Make sure you have MySQL running locally with:
   - Host: `localhost`
   - User: `root`
   - Password: `` (empty) or `root`
   - Database: `ensat`

   The application expects the following tables:
   - `clubs`, `sectors`, `staff`, `students`, `student_club`, `subjects`, `teachers`, `teacher_subject`

### Running the Application

1. **Start both frontend and backend servers:**

```bash
npm run dev:full
```

This command will start:
- **Frontend**: http://localhost:5173
- **Backend**: http://localhost:3001

2. **Alternative: Run servers separately**

```bash
# Terminal 1 - Start the backend server
npm run server

# Terminal 2 - Start the frontend development server
npm run dev
```

## Usage

1. Click the "Record" button to start voice input
2. Speak your query in natural language
3. Alternatively, type your query in the text area
4. Click "Generate SQL" to convert your query
5. View the generated SQL and query results
6. Access your query history using the history button

## Example Queries

Try these sample queries:

- "Show me all customers from California"
- "Find orders with amounts greater than $1000"
- "List all products in the Electronics category"
- "Count the number of completed orders by customer"
- "What are the top 5 selling products this month?"
- "Show me the average order value by customer type"

## Project Structure

```
voice-2-sql/
├── client/              # Frontend React application
│   ├── src/             # Source files
│   ├── public/          # Static assets
│   └── ...
├── server/              # Backend Node.js/Express server
│   ├── controllers/     # Route controllers
│   ├── models/          # Data models
│   ├── routes/          # API routes
│   └── ...
├── .env                 # Environment variables (git-ignored)
├── package.json         # Project dependencies and scripts
└── README.md            # Project documentation
```

## Contributing

Contributions are welcome! Here's how you can contribute to this project:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your code follows the project's coding standards and includes appropriate tests.

## Troubleshooting

### Common Issues

- **Microphone access denied**: Make sure to grant microphone permissions in your browser
- **API key not working**: Verify your OpenAI API key is correctly set in the .env file
- **Connection issues**: Ensure both frontend and backend servers are running

If you encounter any other problems, please check the issues section of the repository or create a new issue.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [OpenAI](https://openai.com/) for providing the natural language processing API
- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) for speech recognition capabilities
- All contributors who have helped improve this project
