
### ▶️  Start the Backend Services

**In one terminal**, start the email API server:

```bash
uvicorn email_server.email_service:app --timeout-keep-alive 1200
```

📍 This runs on: `http://localhost:8000`

It loads a mock inbox with sample emails from emails.db.

**In another terminal**, start the LLM agent server:

```bash
uvicorn email_server.llm_service:app --port 8001 --timeout-keep-alive 1200
```

📍 This runs on: `http://localhost:8001/prompt`

**To run the frontend UI**, simply open `http://localhost:8000/` in a browser.

## 📡 Backend API Reference

The email system is backed by FastAPI and offers these endpoints:

| Method   | Route                       | Description                     |
|----------|----------------------------|---------------------------------|
| `GET`    | `/reset_database`          | Reloads the 5 default emails    |
| `POST`   | `/send`                    | Sends a mock email              |
| `GET`    | `/emails`                  | Lists all emails                |
| `GET`    | `/emails/unread`           | Lists unread emails             |
| `GET`    | `/emails/search?q=...`     | Search by subject/body/sender   |
| `GET`    | `/emails/filter`           | Filter by recipient or date     |
| `GET`    | `/emails/{email_id}`       | Get email by ID                 |
| `PATCH`  | `/emails/{email_id}/read`  | Mark as read                    |
| `PATCH`  | `/emails/{email_id}/unread`| Mark as unread                  |
| `DELETE` | `/emails/{email_id}`       | Delete email                    |

---

## 🧪 Try This Prompt

Paste this into the notebook and watch the tools fire:

```text
Check for unread emails from boss@email.com,
mark them as read,
and send a polite follow-up.
```

You'll see:
- Tool calls executed
- Responses interpreted
- Final message generated

All automatically, via agent reasoning.

---

## ✅ Summary

This project is designed for learners. You’ll:
- Build and run your own agent system
- Watch LLMs call functions, not just generate text
- Understand how reasoning and actions can be chained
- Use `aisuite` to connect prompts to tool execution


---

## 📚 Attribution

This project is adapted from **Module 3** of the course:  
**[Agentic AI](https://learn.deeplearning.ai/courses/agentic-ai)** by DeepLearning.AI

The code has been modified for educational purposes.

---