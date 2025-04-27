# Containerization with Docker: Deploy Anywhere with Ease

Welcome to the Containerization with Docker: Deploy Anywhere with Ease!

In this workshop, you will learn how to:

- Build and run a simple HTML website using Nginx and Docker.
- Build and run a basic Node.js app inside a Docker container.

No prior container experience is needed.

---

## Install Docker

You must install Docker before starting.

### Mac

- If you have a Mac with Apple Silicon (M1/M2) or Intel, download Docker Desktop:
  
  [Download Docker for Mac](https://www.docker.com/products/docker-desktop/)

- Install it like a normal Mac application.
- After installation, start Docker Desktop and keep it running.

---

### Windows

- Install **Docker Desktop for Windows**:
  
  [Download Docker for Windows](https://www.docker.com/products/docker-desktop/)

- **Requirements**:
  - Windows 10 or 11 Pro, Enterprise, or Education.
  - If you have Windows Home, you must enable WSL2 (instructions are on the Docker site).
- After installation, start Docker Desktop and keep it running.

---

### Linux

- For Ubuntu / Debian:

  ```bash
  sudo apt update
  sudo apt install -y ca-certificates curl gnupg
  sudo install -m 0755 -d /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
  sudo chmod a+r /etc/apt/keyrings/docker.gpg
  echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  sudo apt update
  sudo apt install -y docker-ce docker-ce-cli containerd.io
  ```

- Start Docker:

  ```bash
  sudo systemctl start docker
  ```

- Enable Docker to run on boot:

  ```bash
  sudo systemctl enable docker
  ```

- Add your user to the Docker group (optional, so you don't have to use `sudo` every time):

  ```bash
  sudo usermod -aG docker $USER
  ```

  Then logout and login again.

---

## Workshop Structure

### 1. Simple HTML Site with Docker and Nginx

**Location:** `/html-demo/`

**Steps:**

- Build the Docker image:

  ```bash
  docker build -t html-demo ./html-demo
  ```

- Run the container:

  ```bash
  docker run -d --name html-demo -p 8080:80 html-demo
  ```

- Open your browser at [http://localhost:8080](http://localhost:8080).

---

### 2. Simple Node.js App with Docker

**Location:** `/node-demo/`

**Steps:**

- Build the Docker image:

  ```bash
  docker build -t node-demo ./node-demo
  ```

- Run the container:

  ```bash
  docker run -d --name node-demo -p 3000:3000 node-demo
  ```

- Open your browser at [http://localhost:3000](http://localhost:3000).

---

## Folder Structure

```
/html-demo/
  Dockerfile
  index.html

/node-demo/
  Dockerfile
  app.js
  package.json
```

---

## Requirements

- Docker installed on your machine.
- Basic command-line knowledge (copy-paste is enough).
- A modern web browser.

---

## Helpful Docker Commands

- List running containers:

  ```bash
  docker ps
  ```

- Stop a container:

  ```bash
  docker stop <container_name>
  ```

- Remove a container:

  ```bash
  docker rm <container_name>
  ```

- View container logs:

  ```bash
  docker logs <container_name>
  ```

---

## Next Steps (Optional)

After the workshop, try:

- Building more containers.
- Connecting multiple containers using Docker networks.
- Writing a `docker-compose.yml` to automate builds and runs.

---

# Enjoy the Workshop!