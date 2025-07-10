# 🧠 MCP Build Memory Tracker Server

A powerful memory tracking server built using the [MCP (Multi-Service Conversational Platform)](https://github.com/microsoft/mcp) framework. This project monitors, stores, and manages contextual memory from MCP-powered AI applications, enabling smarter and more coherent interactions across sessions.

## 🚀 Features

- 📦 Tracks memory across multiple user sessions  
- 🧩 Integrates seamlessly with MCP client/server setups  
- 🗃️ Uses efficient in-memory and persistent memory stores  
- 🔄 Supports real-time memory updates and deletions  
- ✅ Minimal setup with `uvicorn` for local development  

## 📁 Project Structure

```
Mcp-build-memory-tracker-server/
│
├── memory/                 # Core memory logic and backend
│   ├── memory_store.py     # In-memory and persistent memory handler
│   └── utils.py            # Helper utilities
│
├── server.py              # Main MCP memory tracker server
└── README.md              # You're reading it!
```

## ⚙️ Installation

### 1. Clone the Repository

```
git clone https://github.com/Ramneek82810/Mcp-build-memory-tracker-server.git
cd Mcp-build-memory-tracker-server
```

### 2. Create and Activate Virtual Environment (optional but recommended)

```
python -m venv .venv
source .venv/bin/activate    # On Windows use: .venv\Scripts\activate
```

### 3. Install Dependencies

```
pip install fastapi uvicorn mcp
```

## 🧪 Run the Server Locally

```
uvicorn server:app --reload
```

Or if using `uv` (recommended for MCP projects):

```
uv run server.py
```

The server will be available at `http://localhost:8000`

## 🧠 How Memory Works

- Stores contextual data like conversation history, instructions, and metadata  
- Each memory is scoped by:  
  - `session_id`  
  - `tool_name`  
  - `key`  
- Supports:  
  - `GET /memory`  
  - `POST /memory`  
  - `DELETE /memory`  

## 🔌 Integration with MCP

This server is designed to work with MCP's memory protocol.

### Example MCP Tool Client Usage:

```
from mcp import ClientSession
# Your logic to call memory endpoints
```

Make sure to configure your client to point to this server when running in development mode.

## 📌 Todo

- Add persistent storage backend (Redis/SQLite)  
- Secure memory endpoints  
- Add Swagger UI for API testing  
- Write unit tests  

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.


