# CH-APIS: ConnectiveHobbies Backend

This directory houses the backend API for the ConnectiveHobbies platform. Built on Quarkus and backed by PostgreSQL, it serves as the data and logic hub for the entire platform.

## Tech Stack

- **Backend Framework**: Quarkus
- **Database**: PostgreSQL
- **Authentication**: Keycloak (with OpenID Connect)

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 11 or later.
- Maven
- A running PostgreSQL instance with a database set up for this application.
- (Optional) Docker, if you want to run PostgreSQL as a container.

### Configuration

1. Update the `src/main/resources/application.properties` with your PostgreSQL connection details:

```
quarkus.datasource.db-kind=postgresql
quarkus.datasource.username=YOUR_USERNAME
quarkus.datasource.password=YOUR_PASSWORD
quarkus.datasource.jdbc.url=jdbc:postgresql://localhost:5432/YOUR_DATABASE_NAME
```

2. If you're using Keycloak for authentication, ensure you've set up the appropriate realms, clients, and roles. Then, update the `application.properties` with Keycloak configurations.

### Running the Backend

1. **Compile and run in development mode**:

```
./mvnw compile quarkus:dev
```

This starts the application in development mode with hot-reload capability.

2. **Running with Docker**:

If you have Docker installed, you can also spin up a PostgreSQL instance using:

```
docker run --name connectivehobbies-postgres -e POSTGRES_USER=myuser -e POSTGRES_PASSWORD=mypassword -e POSTGRES_DB=mydatabase -p 5432:5432 -d postgres
```

Remember to update the connection details in the `application.properties` file accordingly.

## API Endpoints

(You can list your main API routes here with brief descriptions.)

- `GET /api/hobbies`: Fetch a list of hobbies.
- `POST /api/hobby`: Add a new hobby.
- ... and so on.

## Testing

Quarkus supports JUnit tests out of the box. To run tests, use:

```
./mvnw test
```
