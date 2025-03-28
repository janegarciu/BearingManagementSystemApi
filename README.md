# Bearing Management API

## Overview

Bearing Management API is a .NET-based web API designed for managing bearings data. This repository includes unit and integration tests and can be configured using user secrets.

## Prerequisites

Ensure you have the following installed:

- .NET SDK 9.0
- Visual Studio 2022 or higher / VS Code with C# extension / Rider

## Getting Started

### Clone the Repository

```sh
git clone https://github.com/janegarciu/BearingManagementSystemApi.git
cd BearingManagementApi
```

### Setup User Secrets

The project uses **user secrets** for storing sensitive information, configure them as follows:

1. Navigate to the project directory containing `BearingManagementApi.csproj`:
   ```sh
   cd BearingManagementApi/BearingManagementApi
   ```
2. Initialize user secrets (if not already initialized):
   ```sh
   dotnet user-secrets init
   ```
3. Set required secrets:
   ```sh
   dotnet user-secrets set "Jwt:Audience" "https://www.bearingManagement.com/"
   dotnet user-secrets set "Jwt:Issuer" "https://www.bearingManagement.com/"
   dotnet user-secrets set "Jwt:ClockSkew" "5"
   dotnet user-secrets set "Jwt:ExpiryHours" "1"
   dotnet user-secrets set "Jwt:Token" "MySuperPuperDuperSecretKey123456789"   ```

### Build and Run the Project

To restore dependencies and build the project cd to BearingManagementApi/BearingManagementApi where the .csproj file is 
located and run these commands:

```sh
dotnet restore
dotnet build
```

To run the API locally:

```sh
dotnet run --urls "https://localhost:7245;http://localhost:5009"
```

The API will be available at `https://localhost:7245/swagger/index.html`.
The API will be available at `http://localhost:5009/swagger/index.html`.

## API Endpoints

### Auth Controller (`/auth`)
- **POST** `/auth/login` - Authenticates a user and returns a token.
- **POST** `/auth/register` - Registers a new user.

### Bearings Controller (`/bearings`)
- **GET** `/bearings` - Retrieves all bearings.
- **GET** `/bearings/{id}` - Retrieves a specific bearing by ID.
- **POST** `/bearings` - Creates a new bearing (requires `Name` and `Type`).
- **PUT** `/bearings/{id}` - Updates an existing bearing.
- **DELETE** `/bearings/{id}` - Deletes a bearing by ID.

## Running Tests

### Unit Tests

To execute unit tests cd to BearingManagementApi/BearingManagementApi_UnitTests and run this command:

```sh
dotnet test 
```

### Integration Tests

To execute integration tests cd to BearingManagementApi/BearingManagementApi_IntegrationTests and run this command:

```sh
dotnet test 
````

### Running with IDE 
Running with IDE is also possible by opening .sln file in IDE and selecting
running profile from the section above.
