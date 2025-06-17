# workshop-prerequisites

This repository contains essential setup instructions and verification steps to ensure you are ready for the upcoming Spring Boot Workshop. Please complete all steps before the workshop begins.

## Before the workshop!

To ensure we hit the ground running, please complete the following setup steps and verification checks before the workshop. This will help you get the most out of our time together.

If you encounter any problems, please create a new [issue](https://github.com/spring-loaded-bootcamp/workshop-prerequisites/issues) in this project, in advance of the workshop.

1. **Operating System**
- macOS / Linux users: You are good to go!
- Windows users: We highly recommend using Windows Subsystem for Linux (WSL) for this workshop. Many of the tools and commands are significantly easier to manage within a Linux environment. Please install WSL and a distribution like Ubuntu. You will perform all subsequent steps within your WSL terminal.

2. **Docker & Docker Compose**
- Download and install Docker Desktop.
- Ensure Docker Desktop is running and configured to start automatically.
- Verify that WSL 2 integration is enabled if you are on Windows.

3. **SDKMAN!**
We'll be using different Java versions, and SDKMAN! is the easiest way to manage them.
- Install [SDKMAN!](https://sdkman.io/)

4. **IntelliJ IDEA Community Edition**
Our workshop will use IntelliJ IDEA. The Community Edition is free and sufficient for this workshop.
- Download IntelliJ IDEA Community Edition from the official JetBrains website: https://www.jetbrains.com/idea/download/

5. **Ngrok**
Ngrok will allow your local applications to be accessible from the public internet, which is crucial for our interactive exercises.

- Sign up for a free account.
- Once signed up, you will be taken to your dashboard.
- Look for your "Auth Token" in the "Your Authtoken" section (e.g., ngrok config add-authtoken <YOUR_AUTH_TOKEN>).

## Validation

```bash
git clone https://github.com/spring-loaded-bootcamp/workshop-prerequisites
cd workshop-prerequisites
```
> Clone the repository and jump into the directory

```bash
docker compose up -d
docker compose ps
```
> Startup the compose.yaml and verify everything is running

You should see something like this:
```text
NAME                                IMAGE                         COMMAND                  SERVICE    CREATED          STATUS                    PORTS
workshop-prerequisites-hello-1      dashaun/hello-spring:v0.0.1   "/cnb/process/web"       hello      13 minutes ago   Up 12 seconds             0.0.0.0:8080->8080/tcp
workshop-prerequisites-ngrok-1      ngrok/ngrok:latest            "/nix/store/1qpvcjc0…"   ngrok      12 seconds ago   Up 12 seconds             0.0.0.0:4040->4040/tcp
workshop-prerequisites-rabbitmq-1   rabbitmq:latest               "docker-entrypoint.s…"   rabbitmq   2 days ago       Up 12 seconds             4369/tcp, 5671/tcp, 15691-15692/tcp, 25672/tcp, 0.0.0.0:5672->5672/tcp
workshop-prerequisites-redis-1      redis:latest                  "docker-entrypoint.s…"   redis      2 days ago       Up 12 seconds (healthy)   0.0.0.0:6379->6379/tcp
```

```bash
sdk install java 17.0.15-librca
sdk install java 24.0.1-librca
sdk use java 24.0.1-librca
java -version
```
> Verify that sdkman is installed and that you can use the installed JDKs

You should see something like this:
```text
openjdk version "24.0.1" 2025-04-15
OpenJDK Runtime Environment (build 24.0.1+11)
OpenJDK 64-Bit Server VM (build 24.0.1+11, mixed mode, sharing)
```

Open a browswer to see if the application is running:
```bash
open http://localhost:8080
```

You should see something like this:
```text
{"id":1,"content":"Hello, World!"}
```

Open a browser to see the Ngrok admin page:
```bash
open http://localhost:4040/status
```
> This page should show your public URL.

Finally, open the public URL, and you should see the similar output as above, from http://localhost:8080.

```text
{"id":2,"content":"Hello, World!"}
```

**You are ready for the workshop!**