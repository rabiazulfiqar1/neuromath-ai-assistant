# NeuroMath AI Assistant

A Python-based AI math solver that leverages LLMs via API integration (FastAPI backend) to solve complex equations and generate step-by-step explanations, with a React frontend for interactive problem solving and history tracking.

## Project Overview
NeuroMath AI Assistant is a comprehensive tool designed to assist users in solving complex mathematical problems using AI. The application combines a FastAPI backend for handling LLM API integrations and a React frontend for a seamless user experience. Users can input mathematical problems, receive detailed step-by-step solutions, and track their problem-solving history.

## Tech Stack

- **Python**: Core programming language for backend development
- **FastAPI**: Modern, fast (high-performance) web framework for building APIs with automatic interactive API documentation
- **React**: A JavaScript library for building user interfaces
- **API Integration**: Integration with Large Language Model (LLM) APIs for solving mathematical problems

## Features

### Backend (FastAPI)
- RESTful API endpoints for receiving math problems
- Integration with LLM APIs (e.g., OpenAI, Anthropic, etc.)
- Processing and parsing LLM responses to extract step-by-step solutions
- History tracking of solved problems
- Secure API key management

### Frontend (React)
- Interactive interface for inputting mathematical problems
- Display of step-by-step solutions
- History section to view previously solved problems
- Responsive design for multiple devices
- State management for user sessions

## Getting Started

### Prerequisites
- Python 3.9+
- Node.js and npm
- LLM API keys (e.g., OpenAI, Anthropic)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ARUNAGIRINATHAN-K/NeuroMath.git
   cd Neuromath-ai-assistant
   ```

2. Set up the backend:
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

3. Set up the frontend:
   ```bash
   cd frontend
   npm install
   ```

4. Create a `.env` file in the backend directory with your LLM API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key
   ANTHROPIC_API_KEY=your_anthropic_api_key
   # Add other API keys as needed
   ```

5. Run the backend:
   ```bash
   uvicorn main:app --reload
   ```

6. Run the frontend:
   ```bash
   npm start
   ```

### Environment Variables

Create a `.env` file in the backend directory with the following variables:

```
OPENAI_API_KEY=your_openai_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
# Add other API keys as needed
```

### API Endpoints

The backend exposes the following main endpoints:

- `POST /solve`: Submit a math problem to be solved by the AI
  - Request Body:
    ```json
    {
      "problem": "string"
    }
    ```
  - Response:
    ```json
    {
      "solution": "string",
      "steps": ["string"],
      "id": "string"
    }
    ```

- `GET /history`: Retrieve the user's solving history
  - Response:
    ```json
    [
      {
        "id": "string",
        "problem": "string",
        "solution": "string",
        "steps": ["string"],
        "created_at": "string"
      }
    ]
    ```

## Usage

1. **Solving a Problem**:
   - Send a POST request to `/solve` with the math problem in the request body.
   - The backend will forward the problem to the configured LLM API, process the response, and return the solution with step-by-step explanations.

2. **Viewing History**:
   - Send a GET request to `/history` to retrieve all previously solved problems.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs, features, or improvements.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For any questions or concerns, please contact the project maintainer or open an issue on GitHub.

---

*Note: This project is currently in progress and under active development. APIs and interfaces may change as development continues.*