## Docker Tennis Data API

This repository contains a Python API for managing a Python API for managing tennis player score data, built with FastAPI, and Dockerized for easy deployment.

### Installation

1. Install Python 3.x.
2. Create and Activate the virtual environment: `. .myenv/scripts/activate`
3. Install required packages: `pip install -r requirements.txt` (automatically done from the dockerfile when running)

### Features
* **CRUD Operations:** Create, read, update, and delete player records.

* **Data Persistence:** Stores player information in a PostgreSQL database.

* **Schema Validation:** Uses Pydantic for data validation and type checking.

* **FastAPI Framework:** Leverages FastAPI for building a robust and efficient API.

* **Docker:** Ensures consistent environments, simplifies deployment, provides lightweight isolation, enables scalability, and integrates with CI/CD for efficient development.

### Database Setup

1. Create a PostgreSQL database.
2. Set the database connection details in the `.env` file. You'll need to add the following:
   ```
   DATABASE_URL=postgresql://<username>:<password>@<host>:<port>/<database_name>
   ```

### DOCKER Setup
1. Download Docker Desktop
2. Create a Dockerfile, with the following;
   ```
   FROM python:3.10

   WORKDIR /Week_7

   COPY . .
   RUN python -m pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt 

   EXPOSE 8000

   CMD ["uvicorn", "api.main:app", "--host", "0.0.0.0", "--port", "8000"]
   ```

3. Build the Docker image by running below:
   ```
   docker build -t Week7 .

   ```
4. After successfull build, Run the Docker container:

   ```
   docker run -it -p 8000:8000 -e MY_ENV_VAR =value Week7
   ```
  

**Running the API:**
 The API will be accessible at `http://localhost:8000`.

### Usage

The API is built with FastAPI and provides CRUD (Create, Read, Update, Delete) operations for tennis players.

**Endpoints:**

* **`/players`**:
    * **GET**: Retrieves a list of all players.
    * **POST**: Creates a new player.
* **`/players/{id}`**:
    * **GET**: Retrieves a specific player by ID.
    * **PUT**: Updates a player by ID.
    * **DELETE**: Deletes a player by ID.


### Notes

* This API is still under development and may be subject to change.
* The database schema and API endpoints may be expanded in the future.
