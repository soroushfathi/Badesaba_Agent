### Project Overview

I built this project using **LangChain** and **LangGraph** with a focus on simplicity, clarity, and practical design choices.

* **Why `langchain.create_agent`?**
  I chose it because it’s optimized and works well with **ReAct-style tool calling**, which fits this use case perfectly.

* **Where does LangGraph fit in?**
  I use **LangGraph checkpoints (SQLite)** to persist graph state per thread, allowing the agent to resume reliably.

* **How is calendar data handled?**
  I convert **Gregorian dates to Jalali** before injecting them into the prompt. The prompt also includes key guidance specific to the Jalali calendar.

* **Why SQLite?**
  SQLite is simple and fast to set up, which makes it ideal for this project. However, it’s not suitable for large-scale systems handling thousands of daily requests. For production-scale use, I would recommend **MongoDB**.

---

### How to Run

```bash
# Install dependencies
uv sync

# Run FastAPI
fastapi dev

# Run Streamlit
streamlit run streamlit_app.py
```

