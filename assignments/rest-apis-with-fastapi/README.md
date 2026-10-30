# 📘 Assignment: Building REST APIs with FastAPI

## 🎯 Objective

Build a REST API for managing tasks using FastAPI, practicing HTTP methods, JSON request and response bodies, and input validation. Use your knowledge of Python functions, dictionaries, and classes to implement and test endpoints with clear success and error responses.

## 📝 Tasks

### 🛠️	Create and Run a FastAPI Application

#### Description
Create a project folder with a virtual environment and a `main.py` file. Install FastAPI using `python -m pip install "fastapi[standard]"`, create a `FastAPI` application named `app`, and run it with `fastapi dev main.py` from that folder.

#### Requirements
Completed program should:

- Start locally at `http://127.0.0.1:8000` without errors.
- Respond to `GET /` with HTTP `200` and the JSON object `{"message": "Task API is running"}`.
- Provide interactive API documentation at `/docs` where you can try your endpoints.
- Keep task data in memory only; no database, authentication, or deployment is required. Data may reset when the server restarts.

### 🛠️	Create and Retrieve Tasks

#### Description
Define a Pydantic request model and use an in-memory dictionary or list to store tasks. Implement endpoints that create tasks, list all tasks, and retrieve one task by its ID.

#### Requirements
Completed program should:

- Accept a JSON body for `POST /tasks` containing a required string `title` with a minimum length of one character and an optional boolean `completed` that defaults to `false`.
- Assign each created task a unique integer `id` that is not reused after deletion during the same server run.
- Return HTTP `201` and the created task, including `id`, `title`, and `completed`.
- Return HTTP `200` and a JSON array from `GET /tasks`, including an empty array when no tasks exist.
- Return HTTP `200` and the matching task from `GET /tasks/{task_id}`.
- Return HTTP `404` with a helpful JSON `detail` message when a task ID does not exist.
- Use FastAPI and Pydantic validation to return HTTP `422` for a missing or empty title, or a non-integer path ID.

For example, sending this body to `POST /tasks`:

```json
{
  "title": "Review Python functions"
}
```

should return a task like this, with the ID assigned by your application:

```json
{
  "id": 1,
  "title": "Review Python functions",
  "completed": false
}
```

### 🛠️	Update, Delete, and Verify Tasks

#### Description
Complete the API with endpoints for replacing and deleting existing tasks. Use `/docs` or an HTTP client such as `curl` to verify the complete create, read, update, and delete workflow, including validation failures and missing tasks.

#### Requirements
Completed program should:

- Accept `PUT /tasks/{task_id}` with both a non-empty string `title` and a boolean `completed` in the JSON body.
- Replace the existing task's title and completion state without changing its ID, returning HTTP `200` and the updated task.
- Return HTTP `422` when a PUT request omits either required field or provides an empty title.
- Delete the matching task through `DELETE /tasks/{task_id}` and return HTTP `204` with no response body.
- Return HTTP `404` with a helpful JSON `detail` message when updating or deleting a task that does not exist.
- Demonstrate that creating a task, retrieving it, marking it completed, and deleting it produces the expected responses; a later GET for the deleted ID must return HTTP `404`.
- Include a file named `api-checks.txt` with the requests, expected status codes, and observed results for that workflow, an empty task list, invalid input, and missing-task errors. Submit it alongside `main.py`.