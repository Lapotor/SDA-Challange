# SDA Coding Challenge - IBAN Checker

## Introduction
This project creates a simple spring boot rest service that validates IBAN numbers.
You can send the URL of a PDF file containing IBAN numbers and the service will check if a blacklisted IBAN number is present in the file.
The URL will be validated against trusted domains to prevent security issues.

## Features
- Endpoint to validate IBAN numbers in a PDF file
- Endpoint to check current time
- Checks for trusted domains

## Design and Security Aspects
- The service is built using Java and Spring Boot.
- Communication is handled via REST.
- Security considerations include validating input URLs and handling sensitive data securely.

## Future thoughts
- Load the blacklist from a database
- Only allow requests with a valid API key

## Getting Started

### Prerequisites
- Java 21 or higher
- Maven 3
- Docker

### Installation
1. Clone the repository
   ```sh
   git clone https://github.com/Lapotor/SDA-Challange.git
   cd SDA-Challange
   ```
2. Build the project
   ```sh
   mvn clean install
   ```
3. Run the project
   ```sh
   mvn spring-boot:run
   ```
   
### Usage
Send a POST request to the `/api/v1/check` endpoint with a JSON payload containing the document URL.
```sh
curl -X POST "http://localhost:8080/api/v1/check" -H "Content-Type: application/json" -d '{"url": "http://example.com/document.pdf"}'
```

## License
This project is licensed under the MIT License - see the [`LICENSE`](LICENSE) file for details.