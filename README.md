# Contacts Management System 📇

A containerized RESTful API for managing contacts, featuring a **FastAPI** backend and a **MySQL** database. This project demonstrates the use of Docker Compose, persistent volumes, and clean Python architecture.

---

## 🚀 Quick Start Guide

### 1. Clone the Project
First, download the project to your local machine by running the following command:
```bash
git clone [https://github.com/dforst25/week10_contacts.git](https://github.com/dforst25/week10_contacts.git)
cd contact_project

```

### 2. Port Management

Ensure that no other container is currently using port **8000**:

```bash
docker ps --filter "publish=8000"

```

### 3. Manage Existing Containers (If Necessary)

If a container is already running on port 8000, stop it to avoid conflicts:

```bash
docker stop <container_name_or_id>

```

### 4. Start the Server

Run the following command to build and start the project in detached mode:

```bash
docker compose up -d --build

```

> **Note:** Please allow about 20-30 seconds for the database to initialize and run the setup scripts before testing the endpoints.

### 5. Test the API Endpoints

Once the containers are running, you can access the interactive API documentation (Swagger UI) in your browser:

**URL:** [http://localhost:8000/docs](https://www.google.com/search?q=http://localhost:8000/docs)

From this interface, you can perform CRUD operations:

* **GET** `/contacts` - Retrieve all contacts.
* **POST** `/contacts` - Create a new contact.
* **PUT** `/contacts/{id}` - Update an existing contact.
* **DELETE** `/contacts/{id}` - Remove a contact.

### 6. Clean Up

To stop and remove the project containers when you are finished:

```bash
docker compose down

```

### 7. Restore Previous Environment

If you stopped a container in step 3, don't forget to restart it:

```bash
docker start <container_name_or_id>

```

---

## 🛠️ Command Line Testing (CURL)

If you prefer testing via terminal (PowerShell), use these examples:

**Create a Contact:**

```powershell
curl.exe -X POST http://localhost:8000/contacts -H "Content-Type: application/json" -d "{`"first_name`":`"Test`",`"last_name`":`"User`",`"phone_number`":`"050-9999999`"}"

```

**Get All Contacts:**

```powershell
curl.exe http://localhost:8000/contacts

```

---

## 📦 Project Structure

```text
.
├── app/
│   ├── main.py            # FastAPI Routes & App Entry Point
│   ├── data_interactor.py # Database Logic (CRUD Class)
│   ├── contact.py         # Contact Model & Logic
│   ├── Dockerfile         # API Container Blueprint
│   └── requirements.txt   # Python Dependencies
├── sql/
│   └── init.sql           # Database Schema Setup
├── .env                   # Environment Variables (DB Credentials)
└── docker-compose.yaml    # Services Orchestration

```
