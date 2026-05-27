# CS209A_project

## Project Overview

In the process of software development, many questions will arise. Developers may resort to Q&A website to
post questions and seek answers.

Stack Overflow is such a Q&A website for programmers, and it belongs to the Stack Exchange Network. Stack
Overflow serves as a platform for users to ask and answer questions, and, through membership and active
participation, to vote questions and answers up or down and edit questions and answers in a fashion similar
to a wiki. Users of Stack Overflow can earn reputation points and "badges"; for example, a person is awarded
10 reputation points for receiving an "up" vote on a question or an answer to a question, and can receive
badges for their valued contributions. Users unlock new privileges with an increase in reputation, like the
ability to vote, comment, and even edit other people's posts.

In this final project, we use Spring Boot to develop a web application that stores, analyzes, and visualizes
Stack Overflow Q&A data related to Java programming. The goal is to understand common questions,
answers, and resolution activities in Java-related Stack Overflow threads.

## Getting Started

### Requirements

- JDK 17
- Maven 3.9+ or another Maven-compatible build tool
- PostgreSQL running on `localhost:5432`
- A database named `cs209a_grace`
- Source data in `data_2000_new`

### Configuration

The main configuration file is `FinalProject_demo/src/main/resources/application.properties`.

- Web port: `8081`
- Database URL: `jdbc:postgresql://localhost:5432/cs209a_grace`
- Username: `postgres`
- Password: `huarui66`
- JPA mode: `validate`, so the database schema must already exist and match the entities

### Run the Web App

From the repository root, enter the `FinalProject_demo` directory and run:

```powershell
cd FinalProject_demo
mvn spring-boot:run
```

After startup, open:

```text
http://localhost:8081/
```

### Data Import

The repository includes two data-related entry points:

- `src/main/java/importdata/InsertDatabase.java` imports local JSON data into PostgreSQL
- `src/main/java/importdata/StackOverflowDataCollector.java` collects data from the Stack Overflow API

Both classes contain default paths or parameters, so make sure they match your local environment before running them, especially the data directory and database password.

### Note

If you want a quick summary of runtime requirements, see `requirements.txt` in the repository root.

