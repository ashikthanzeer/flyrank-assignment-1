# AI Study Assistant

An AI‑powered study assistant that helps students **organize learning materials**, **generate concise summaries**, and **answer questions** using a Retrieval‑Augmented Generation (RAG) pipeline.

---

## Tech Stack

- **Frontend**: Next.js (React) with TypeScript and Tailwind CSS for a modern, responsive UI.
- **Backend API**: FastAPI (Python) exposing endpoints for document ingestion, vector store search, and LLM inference.
- **Database**: PostgreSQL stores user metadata, uploaded documents references, and session history.
- **LLM Provider**: Any compatible AI/LLM API (e.g., OpenAI, Anthropic) configured via environment variables.

---

## Getting Started

### Prerequisites

- **Node.js** (v20 or later) and **npm** (or **pnpm**/**yarn**) installed.
- **Python** (>=3.10) and **pip**.
- **PostgreSQL** instance (local or remote) with a database created for the project.
- An **API key** for the chosen LLM provider.

### 1. Clone the repository

```bash
git clone <repository-url>
cd flyrank-assignment-1
```

### 2. Set up the backend

```bash
# Create a virtual environment
python -m venv venv
source venv/Scripts/activate  # Windows

# Install Python dependencies
pip install -r backend/requirements.txt
```

Create a `.env` file in the `backend/` directory with the required variables:

```
POSTGRES_URL=postgresql://user:password@localhost:5432/flyrank
LLM_API_KEY=your-llm-api-key
LLM_ENDPOINT=https://api.openai.com/v1/chat/completions
```

Run database migrations (if using Alembic) and start the FastAPI server:

```bash
alembic upgrade head  # optional, if migrations are set up
uvicorn backend.main:app --reload --port 8000
```

The API will be available at `http://localhost:8000`.

### 3. Set up the frontend

```bash
cd frontend
npm install
```

Create a `.env.local` file in the `frontend/` directory:

```
NEXT_PUBLIC_API_URL=http://localhost:8000
```

Start the development server:

```bash
npm run dev
```

Visit `http://localhost:3000` in your browser to interact with the AI Study Assistant.

---

## Planned Features

- Document upload (PDF, DOCX, TXT) with chunking and vector indexing.
- AI‑powered question answering over uploaded documents.
- Automatic summarisation of long texts.
- Personal study material organization (folders, tags, notes).
- User authentication and session persistence.

---

## Project Structure

```
flyrank-assignment-1/
├─ frontend/          # Next.js app (app/, components/, lib/)
├─ backend/           # FastAPI service (api/, models/, db/)
├─ README.md          # This documentation
├─ AGENTS.md          # Project conventions and guidelines
└─ .gitignore
```

---

## Contributing

Please follow the conventions outlined in **AGENTS.md**:
- Use **TypeScript** for all frontend code.
- Write **functional React components**.
- Keep API logic separate from UI components.
- Follow **Conventional Commits** for all commits.
- Ensure code is linted and formatted before submitting a PR.

---

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.