# Lab 7 - GitHub Actions CI

Java calculator example for SE 4111 Lab 7.

## Requirements
- Java JDK 17+
- Maven 3.6+
- Git

## Test locally
```bash
mvn clean test
```
Expected: three passing JUnit 5 tests.

## GitHub setup
1. Create an empty GitHub repository named `calculator-app`.
2. Open a terminal in this folder and run:
```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/calculator-app.git
git push -u origin main
```
3. Open your repository's Actions tab. The Java CI workflow should run.

## Activity 2: Intentionally fail CI
1. In `src/main/java/com/example/Calculator.java`, change `return a + b;` to `return a - b;`.
2. Run:
```bash
git add src/main/java/com/example/Calculator.java
git commit -m "intentional bug to test CI"
git push
```
3. Open Actions and view the failing test logs.
4. To restore the working project, change the operation back to `+` and commit/push again.

## Note
Based on the lab PDF. The Maven Surefire plugin is explicitly set to version 3.2.5 to support JUnit 5 reliably; this is an additional compatibility setting beyond the minimal pom.xml shown in the slides.
