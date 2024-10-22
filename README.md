
# Task Manager App

A RESTful API for managing tasks built with **FastAPI** and **MongoDB**, containerized using **Docker** and **Docker Compose**.

## Features

- Create, retrieve, update, and delete tasks.
- Retrieve tasks by ID or title.
- Easily deployable with **Docker Compose**.
- Designed to be scalable and maintainable with a modular structure.

## Prerequisites

- [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/) installed.
- **Python 3.9+** if running the app locally.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/task-manager-app.git
cd task-manager-app
```

### 2. Environment Setup

Create a `.env` file with the following content:

```env
MONGO_INITDB_ROOT_USERNAME=your_mongodb_username
MONGO_INITDB_ROOT_PASSWORD=your_mongodb_password
```

### 3. Build and Run the Application

To build and start the services using **Docker Compose**, run:

```bash
docker compose up --build
```

The application will be available at `http://localhost:8000`.

### 4. API Endpoints

Refer to the **API Documentation** for detailed information on each endpoint:

- **Create a Task**
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"title":"Task title","description":"Task description"}' http://localhost:8000/tasks
    ```

- **Get Task by ID**
    ```bash
    curl --silent http://localhost:8000/tasks/{task_id} | jq
    ```

- **Get Task by Title**
    ```bash
    curl --silent http://localhost:8000/tasks/title/{task_title} | jq
    ```

- **Get All Tasks**
    ```bash
    curl --silent http://localhost:8000/tasks | jq
    ```

- **Delete Task by ID**
    ```bash
    curl --silent -X DELETE http://localhost:8000/tasks/{task_id} | jq
    ```

For more details, see the [API Documentation](./api_documentation.md).

## Running Locally (Without Docker)

1. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

2. Run the application:
    ```bash
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

3. Access the app at `http://localhost:8000`.

## Project Structure

```plaintext
task-manager-app/
│
├── main.py                 # FastAPI app entry point
├── Dockerfile              # Docker instructions for building the app image
├── docker-compose.yaml     # Docker Compose setup for the app and MongoDB
├── requirements.txt        # Python dependencies
├── LICENSE.txt             # License information
└── api_documentation.md    # API usage examples and documentation
```

## License

This project is licensed under the **MIT License**. See the [LICENSE.txt](./LICENSE.txt) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have suggestions or improvements.

## Contact

Created by **Patrick Schneider** in the **Hyperskill.org** course *DevOps Engineering with AI*  - feel free to reach out for any questions or feedback!

