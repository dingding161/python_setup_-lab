# python_setup_-lab
.\venv\Scripts\Activate.ps1
(venv) PS C:\...\python_setup_lab>
/projects/{project_id}/tasks
| Parameter | Type | Required | Description |
|---|---|---|---|
| `project_id` | string | Yes | The unique ID of the project where the task will be created. |
| Parameter | Type | Required | Description |
|---|---|---|---|
| `title` | string | Yes | The name of the task. |
| `description` | string | No | Additional information about the task. |
| `assignee_id` | string | Yes | The ID of the user assigned to the task. |
| `due_date` | string | Yes | The task deadline in `YYYY-MM-DD` format. |
| `priority` | string | Yes | The task priority. Accepted values are `low`, `medium`, or `high`. |
| Header | Required | Description |
|---|---|---|
| `Authorization` | Yes | Contains the authentication token. |
| `Content-Type` | Yes | Must be `application/json` because the request body uses JSON. |
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json
POST /projects/proj_1001/tasks
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json
{
  "title": "Complete project documentation",
  "description": "Write and review the project user manual.",
  "assignee_id": "user_2045",
  "due_date": "2026-10-20",
  "priority": "high"
}| HTTP Code | Meaning |
|---|---|
| `201 Created` | The task was successfully created. |
| `400 Bad Request` | The request contains invalid or missing data. |
| `401 Unauthorized` | The authentication token is missing or invalid. |
| `403 Forbidden` | The authenticated user does not have permission to create tasks in the project. |
| `404 Not Found` | The specified project or assignee does not exist. |
| `409 Conflict` | The request conflicts with the current project data. |
| `422 Unprocessable Entity` | The request format is valid, but one or more values fail validation. |
| `500 Internal Server Error` | An unexpected error occurred on the server. |
{
  "id": "task_7842",
  "project_id": "proj_1001",
  "title": "Complete project documentation",
  "description": "Write and review the project user manual.",
  "assignee_id": "user_2045",
  "due_date": "2026-10-20",
  "priority": "high",
  "status": "todo",
  "created_at": "2026-10-08T09:30:00Z"
}

