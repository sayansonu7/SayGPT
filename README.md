# SayGPT 🤖

A smart personal assistant chatbot powered by Groq AI and web search capabilities. SayGPT can answer questions, perform web searches, and maintain conversation context using advanced caching.

## ✨ Features

- **AI-Powered Conversations**: Uses Groq's Llama 3.3 70B model for intelligent responses
- **Web Search Integration**: Real-time web search using Tavily API
- **Context Awareness**: Maintains conversation history with thread-based caching
- **Dual Interface**: Available as both CLI application and web interface
- **Fast Response Times**: Optimized for quick interactions
- **Secure API Handling**: Environment-based configuration for API keys

## 🚀 Quick Start

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- API Keys:
  - [Groq API Key](https://console.groq.com/)
  - [Tavily API Key](https://tavily.com/)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/sayansonu7/SayGPT.git
   cd SayGPT
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```

   Edit `.env` and add your API keys:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   TAVILY_API_KEY=your_tavily_api_key_here
   ```

## 💻 Usage

### CLI Interface

Run the chatbot in your terminal:

```bash
node app.js
```

Start chatting! Type your questions and press Enter. Type "bye" to exit.

**Example:**
```
You: What is the current weather in Mumbai?
Assistant: [AI response with web search if needed]

You: bye
```

### Web Interface

1. **Start the server**
   ```bash
   node server.js
   ```

2. **Open your browser**
   ```
   http://localhost:3000
   ```

3. **Start chatting** through the web interface

## 🛠️ API Endpoints

### POST /chat
Send a message to the chatbot.

**Request Body:**
```json
{
  "message": "Your question here",
  "threadId": "unique-thread-identifier"
}
```

**Response:**
```json
{
  "message": "AI response here"
}
```

**Example:**
```bash
curl -X POST http://localhost:3000/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello!", "threadId": "user123"}'
```

## 🏗️ Project Structure

```
SayGPT/
├── app.js              # CLI chatbot application
├── server.js           # Express server for web interface
├── chatbot.js          # Core chatbot logic with AI and search
├── frontend/
│   ├── index.html      # Web interface
│   └── script.js       # Frontend JavaScript
├── .env.example        # Environment variables template
├── .gitignore          # Git ignore rules
├── package.json        # Dependencies and scripts
└── README.md           # This file
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GROQ_API_KEY` | Your Groq API key | Yes |
| `TAVILY_API_KEY` | Your Tavily API key | Yes |

### Customization

- **Model Selection**: Modify the model in `chatbot.js` (currently using `llama-3.3-70b-versatile`)
- **Cache TTL**: Adjust cache expiration in `chatbot.js` (default: 24 hours)
- **Port**: Change server port in `server.js` (default: 3000)

## 🤝 How It Works

1. **User Input**: Receives message and thread ID
2. **Context Loading**: Retrieves conversation history from cache
3. **AI Processing**: Sends message to Groq API with conversation context
4. **Tool Calling**: If needed, performs web search using Tavily API
5. **Response Generation**: Returns AI response
6. **Context Saving**: Updates conversation cache

## 📦 Dependencies

- **groq-sdk**: Groq AI API client
- **@tavily/core**: Web search API client
- **express**: Web server framework
- **cors**: Cross-origin resource sharing
- **node-cache**: In-memory caching
- **readline**: CLI input handling

## 🔒 Security

- API keys are stored in environment variables
- `.env` file is gitignored to prevent accidental commits
- Use `.env.example` as a template for required variables

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Commit your changes: `git commit -am 'Add feature'`
5. Push to the branch: `git push origin feature-name`
6. Submit a pull request

## 📄 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Groq](https://groq.com/) for providing fast AI inference
- [Tavily](https://tavily.com/) for web search capabilities
- [Node.js](https://nodejs.org/) for the runtime environment

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/sayansonu7/SayGPT/issues) page
2. Create a new issue with detailed information
3. Include error messages and steps to reproduce

---

**Happy chatting with SayGPT! 🚀**