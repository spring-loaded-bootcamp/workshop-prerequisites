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
git clone github.com/spring-loaded-bootcamp/workshop-prerequisites
cd workshop-prerequisites
```
> Clone the repository and jump into the directory

```bash
docker compose up -d
docker ps
```
> Startup the compose.yaml and verify everything is running

You should see something like this:
```text
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
```


