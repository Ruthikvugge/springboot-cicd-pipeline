# Spring Boot CI/CD Pipeline — GitHub Actions

A simple CI/CD setup for a Java Spring Boot app using GitHub Actions. Every push to main automatically builds the project and runs tests.

---

## What it does

- Triggers on every push or pull request to `main`
- Sets up Java 17 environment
- Builds the project using Maven
- Runs unit tests and reports the result

---

## Tech used

- Java 17 + Spring Boot
- Maven
- GitHub Actions
- JUnit (testing)

---

## Workflow

```yaml
name: Java Spring Boot CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Java 17
        uses: actions/setup-java@v3
        with:
          java-version: '17'
          distribution: 'temurin'

      - name: Build with Maven
        run: mvn clean install -DskipTests

      - name: Run Tests
        run: mvn test
```

---

## How to run locally

```bash
git clone https://github.com/Ruthikvugge/springboot-cicd-pipeline.git
cd springboot-cicd-pipeline
mvn clean install
mvn spring-boot:run
```

---

## Project structure

```
├── .github/
│   └── workflows/
│       └── ci.yml
├── src/
│   ├── main/java/
│   └── test/java/
└── pom.xml
```

---

## Author
Ruthik — DevOps Engineer 
[LinkedIn](https://linkedin.com/in/ruthik-varma-715a653b4) | [GitHub](https://github.com/Ruthikvugge)

[LinkedIn](https://linkedin.com/in/ruthik-varma-715a653b4) | [GitHub](https://github.com/Ruthikvugge)

