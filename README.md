# mini-rag

This is a minimal implementation of a **Retrieval-Augmented Generation (RAG)** system for question answering.
The project demonstrates how to go from notebooks to a more production-oriented setup.


## Requirements

- Python 3.11
- Git
- Miniconda
- (Optional but recommended) WSL2 on Windows


## Install Python using Miniconda

1. Download and install **Miniconda** from the official website:
   https://docs.conda.io/en/latest/miniconda.html

2. Create a new conda environment:

   ```bash
   $ conda create -n mini-rag-app python=3.11
   ```

3. Activate the environment:

   ```bash
   $ conda activate mini-rag-app
   ```

### (Optional) Setup you command line for better readability


   ```bash
   export PS1="\[\033[01;32m\]\u@\h:\w\n\[\033[00m\]\$ "
   ```

---

## Installation

### Install the required packages

   ```bash
   $ pip install -r requirements.txt
   ```

### Setup the environment variables

   ```bash
   $ cp .env.example .env
   ```

Set your environment variables in the `.env` file. Like `OPENAI_API_KEY` value.

---

## Run Docker Compose Services

```bash
   $ cd docker
   $ cp .env.example .env
```

- Update `.env` with your credentials

## Run the FastAPI server

```bash
$ uvicorn main:app --reload --host 0.0.0.0 --port 5000
```

---

## reset docker(assets, ...)


   ```bash
   sudo docker stop $(sudo docker ps -aq)
   ```
   
   ```bash
   sudo docker rm $(sudo docker ps -aq)
   ```
   
   ```bash
   sudo docker rmi $(sudo docker images -q)
   ```
   
   ```bash
   sudo docker volume rm $(sudo docker volume ls -q)
   ```
   
   ```bash
   sudo docker system prune --all
   ```

Run docker-compose

   ```bash
   sudo docker compose up -d
   ```
