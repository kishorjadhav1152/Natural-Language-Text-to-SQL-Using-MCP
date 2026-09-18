# 🤖 Natural Language Text-to-SQL Using MCP

An **Agentic AI project** that allows users to interact with a SQL database using **natural language** instead of writing SQL queries manually.

The project uses the **Model Context Protocol (MCP)** to connect an AI client with a SQL database and generate/execute SQL queries based on natural-language questions.

---

## 🚀 Project Overview

Traditional database interaction requires users to have SQL knowledge.

For example, a user normally needs to write:

```sql
SELECT * FROM students WHERE age > 20;
```

With this project, the user can simply ask:

```text
Show me all students whose age is greater than 20.
```

The AI system interprets the natural-language request, generates the appropriate SQL query, communicates with the MCP server, executes the query against the database, and returns the result.

---

## ✨ Features

* 🗣️ **Natural Language to SQL**
* 🤖 **Agentic AI workflow**
* 🔌 **Model Context Protocol (MCP) integration**
* 🗄️ **SQLite database integration**
* ⚡ Automatic SQL query generation
* 🔍 Database querying through natural language
* 🔗 MCP Client–Server architecture
* 🐍 Python-based implementation
* 📊 Query results returned to the user

---

## 🏗️ Architecture

```text
                    User
                     │
                     ▼
          ┌─────────────────────┐
          │ Natural Language    │
          │ Question            │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │     MCP Client      │
          │   mcp_client.py     │
          └──────────┬──────────┘
                     │
                     │ MCP
                     ▼
          ┌─────────────────────┐
          │     MCP Server      │
          │   mcp_server.py     │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │     SQL Engine      │
          │      sql.py         │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │    SQLite Database  │
          │     student.db     │
          └──────────┬──────────┘
                     │
                     ▼
                  Result
                     │
                     ▼
                   User
```

---

## 🛠️ Technologies Used

| Technology                  | Purpose                           |
| --------------------------- | --------------------------------- |
| Python                      | Core programming language         |
| MCP                         | AI-to-tool/database communication |
| SQLite                      | Database                          |
| SQL                         | Database querying                 |
| Natural Language Processing | Understanding user questions      |
| Agentic AI                  | Intelligent query generation      |
| MCP Client                  | Sends requests to MCP server      |
| MCP Server                  | Exposes database functionality    |

---

## 📂 Project Structure

```text
Natural-Language-Text-to-SQL-Using-MCP/
│
├── mcp_client.py       # MCP client implementation
├── mcp_server.py       # MCP server and database tools
├── sql.py              # SQL/database functionality
├── student.db          # SQLite sample database
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Natural-Language-Text-to-SQL-Using-MCP.git
```

Move into the project directory:

```bash
cd Natural-Language-Text-to-SQL-Using-MCP
```

---

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv venv
```

Activate it:

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

Run:

```bash
pip install -r requirements.txt
```

---

# ▶️ Running the Project

The project contains two main components:

### MCP Server

```bash
python mcp_server.py
```

### MCP Client

In another terminal:

```bash
python mcp_client.py
```

Follow the prompts provided by the application.

> The exact startup command can depend on how the MCP client/server are configured in your environment.

---

# 💬 Example Queries

After starting the application, users can ask questions such as:

```text
Show all students.
```

```text
How many students are in the database?
```

```text
Show students older than 20.
```

```text
Show the names of all students.
```

```text
Find students from Mumbai.
```

```text
What is the average age of the students?
```

The system converts the natural-language request into a SQL operation and retrieves the corresponding result from the database.

---

# 🔄 How It Works

### 1. User Input

The user provides a question in natural language.

```text
"Show students older than 20."
```

### 2. MCP Client

The MCP client receives the user's request and communicates with the MCP server.

### 3. MCP Server

The MCP server exposes database-related functionality to the client.

### 4. SQL Generation

The natural-language request is translated into an SQL query.

Example:

```sql
SELECT *
FROM students
WHERE age > 20;
```

### 5. Database Execution

The SQL query is executed against the SQLite database:

```text
student.db
```

### 6. Result

The database result is returned to the user.

---

# 🔌 What is MCP?

**Model Context Protocol (MCP)** is a protocol designed to allow AI applications to interact with external tools, resources, and data sources through a standardized interface.

In this project, MCP provides the communication layer between the AI/client side and the database functionality exposed by the server.

```text
AI Application
      │
      ▼
  MCP Client
      │
      │ MCP
      ▼
  MCP Server
      │
      ▼
 Database Tools
      │
      ▼
 SQLite
```

---

# 🎯 Use Cases

This architecture can be extended to applications such as:

* 📊 Business analytics
* 🏦 Financial data analysis
* 🛒 E-commerce analytics
* 👥 Customer databases
* 🏫 Student management systems
* 📈 Business intelligence
* 🗄️ Enterprise database querying
* 🤖 AI-powered data assistants

---

# 🔐 Security Considerations

When connecting an AI system to a real database, additional security controls should be implemented.

Recommended controls include:

* Read-only database access where possible
* SQL query validation
* Input validation
* Authentication and authorization
* Query allowlists
* Protection against destructive SQL commands
* Database credentials stored in environment variables
* Logging and monitoring

**Do not expose production database credentials in the source code or GitHub repository.**

---

# 🚧 Future Improvements

Possible improvements include:

* [ ] Add support for PostgreSQL
* [ ] Add MySQL support
* [ ] Add multiple database connections
* [ ] Add database schema discovery
* [ ] Add SQL query validation
* [ ] Add query history
* [ ] Add Streamlit web interface
* [ ] Add visualization of query results
* [ ] Add authentication
* [ ] Add read-only database mode
* [ ] Add Docker support
* [ ] Add automated tests
* [ ] Add support for complex joins
* [ ] Add natural-language data visualization

---

# 📌 Important Notes

This project uses a sample SQLite database for demonstration purposes.

Before connecting an AI agent to a production database:

1. Restrict database permissions.
2. Validate generated SQL.
3. Prevent destructive operations.
4. Protect database credentials.
5. Test generated queries carefully.
6. Monitor database access.

---

# 📜 License

You can use the **MIT License** if you want to make this project open source.

Add a `LICENSE` file to the repository if you choose to publish it under MIT.

---

# 👨‍💻 Author

**Kishor Jadhav**

AI / Machine Learning | Data Science | Agentic AI

---

## ⭐ If You Find This Project Useful

Give the repository a ⭐ on GitHub and feel free to explore, improve, and extend the project.
