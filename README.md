# Flask + PostgreSQL Dockerized App

This project demonstrates how to containerize a simple Flask web application and connect it to a PostgreSQL database using Docker Compose. The goal is to build and run both containers (web and database) together and validate the communication between them.

---

## 🚀 Features

- 🐍 Flask web app containerized with Docker
- 🐘 PostgreSQL container with persistent storage
- 🔗 Docker Compose to manage multi-container setup
- ✅ Database connectivity validated using `psql` inside the web container

---

## 📁 Project Structure

.
├── app.py # Flask application   
├── Dockerfile # Builds the web container   
├── requirements.txt # Python dependencies   
├── docker-compose.yml # Multi-container setup   
├── screenshots/ # Validation screenshots   
│ ├── psql_output.png   
│ └── web_app_browser.png   
└── README.md # Project documentation   


---

## ⚙️ Setup Instructions

### 1. Clone the Repository

    ```
    git clone https://github.com/your-username/flask-postgres-docker.git
    cd flask-postgres-docker

2. Run Docker Compose
    ```
    docker-compose up -d --build
    
This will:

Build the Flask app using the Dockerfile

Start both web and db containers

🔗 Validate Container Communication
1. Access Web Container
    ```
    docker exec -it <web_container_id_or_name> bash

2. Install PostgreSQL Client & Connect
bash
Copy
Edit
apt update && apt install -y postgresql-client
psql -h db -U user -d mydb
📸 A screenshot of the successful connection is in screenshots/psql_output.png

🌐 Access the Web Application
Open your browser and go to:
http://localhost:5000

📸 A screenshot of the running app is in screenshots/web_app_browser.png

📝 Environment Variables
The environment variables for PostgreSQL are passed in docker-compose.yml:

POSTGRES_USER: user
POSTGRES_PASSWORD: password
POSTGRES_DB: mydb
These are accessible to both the db and web containers for seamless connection.

📸 Screenshots
![Screenshot 2025-05-28 134051](https://github.com/user-attachments/assets/5d631858-d762-4f51-9a61-7c466e4739ff)
![Screenshot 2025-05-28 134114](https://github.com/user-attachments/assets/f3995ab5-f3bc-4d6f-b8d7-19a0560628cf)


📦 Technologies Used
Python 3

Flask

PostgreSQL

Docker

Docker Compose
