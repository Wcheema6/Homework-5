# Campus Task Board API

## Project Description

Campus Task Board API is a simple backend application built using Spring Boot. It allows users to manage tasks through a REST API.

Users can:
- Create tasks
- View all tasks
- View a task by ID
- Update tasks
- Delete tasks

Each task includes:
- id
- title
- description
- completed (true/false)
- priority (LOW, MEDIUM, HIGH)

For Homework 5, tasks are stored in memory using an ArrayList, so all data will be lost when the application is restarted.

---

## How to Run the Application

1. Open the project folder in VS Code or IntelliJ.

2. Make sure Java 17 or newer is installed.

3. Open a terminal inside the project folder.

4. Run the application:

```bash
./mvnw spring-boot:run

For Windows:

mvnw.cmd spring-boot:run
Wait until you see:
Started CampusTaskboardApplication
Open your browser and go to:
http://localhost:8080/api/tasks

If it works, you should see:

[]
API Endpoints Documentation

Base URL:

http://localhost:8080/api/tasks
GET all tasks

GET /api/tasks

Returns all tasks.

Example:

[
  {
    "id": 1,
    "title": "My first task",
    "description": "Testing my API",
    "completed": false,
    "priority": "HIGH"
  }
]
GET task by ID

GET /api/tasks/{id}

Example:

http://localhost:8080/api/tasks/1

Returns a single task.
If not found → 404 error.

POST create a task

POST /api/tasks

Body:

{
  "title": "My first task",
  "description": "Testing my API",
  "completed": false,
  "priority": "HIGH"
}

Response:

{
  "id": 1,
  "title": "My first task",
  "description": "Testing my API",
  "completed": false,
  "priority": "HIGH"
}
PUT update a task

PUT /api/tasks/{id}

Example:

http://localhost:8080/api/tasks/1

Body:

{
  "title": "Updated Task",
  "description": "Updated description",
  "completed": true,
  "priority": "LOW"
}

Returns updated task.

DELETE a task

DELETE /api/tasks/{id}

Example:

http://localhost:8080/api/tasks/1

Response:

204 No Content
Validation Example

If invalid data is sent:

{
  "title": "AB"
}

Response:

{
  "title": "Title must be between 3 and 100 characters"
}
