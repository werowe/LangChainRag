This Jupyter notebook sets up a question-answering system for a financial database using LangChain, MySQL, and the Ollama LLM. It automatically converts natural language finance questions into SQL, runs the queries, and produces user-friendly answers.

---

### Step-by-Step Breakdown

#### 1. **Imports and Setup**
- Imports necessary libraries from LangChain and Python for database access, model prompt handling, and type annotations.
- Sets up a MySQL connection to the `finances` database using a password.

#### 2. **LLM and Prompt Template**
- Initializes the Ollama local LLM (Llama 3.1) as a SQL expert.
- Uses a prompt template that instructs the model to generate syntactically correct MySQL queries, referencing allowed tables/columns.

#### 3. **Schema and Prompt Formatting**
- Defines classes (`State`, `QueryOutput`) for the information passed between pipeline steps.
- Uses LangChain's SQL chain to generate a prompt and inject real database schema information and column names.

#### 4. **Generate SQL From User Question**
- Converts a user's natural language question (e.g., "How much money did I spend in February 2024?") into a SQL statement via an LLM with structured output validation.

#### 5. **Run the SQL Query**
- Executes the generated SQL against the live MySQL database and returns the results.

#### 6. **Answer Generation**
- Uses the LLM to combine the original question, generated SQL, and SQL result into a final natural language answer for the user.

---

### Example Workflow

- The question "How much money did I spend in February 2024?" is translated to a valid SQL query:
