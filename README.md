# MatchConnect.FullStack

A full-stack social matchmaking application built with ASP.NET Core and a single-page application frontend.

This project demonstrates modern web application development concepts including:
- authentication
- authorization
- RESTful APIs
- route protection
- media uploads
- client-side routing

## Features

### Backend API

* User registration and login
* JWT-based authentication
* Claims-based authorization
* User profile management
* Photo upload and management
* Set main profile photo
* Delete profile photos
* Messaging functionality
* RESTful API architecture
* DTO mapping with AutoMapper
* Cloud-based image hosting with Cloudinary
* SQLite database integration with Entity Framework Core

### Frontend SPA

* Client-side routing
* Route guards for protected pages
* Resolvers for preloading data
* Custom pipes
* Navigation/auth state handling
* Responsive UI

## Technologies Used

### Backend

* ASP.NET Core 2.2
* C#
* Entity Framework Core
* SQLite
* AutoMapper
* Cloudinary
* JWT Authentication

### Frontend

* Angular / SPA framework
* TypeScript
* HTML / CSS
* Bootstrap

## Solution Structure

```text
MatchConnect.FullStack/
│
├── MatchConnect.API/
│   ├── Controllers/
│   │   ├── AuthController.cs
│   │   ├── UsersController.cs
│   │   ├── PhotosController.cs
│   │   └── MessagesController.cs
│   │
│   ├── Data/
│   ├── Models/
│   ├── Dtos/
│   ├── Helpers/
│   └── MatchConnect.API.csproj
│
├── MatchConnect.Client/
│   ├── src/app/
│   │   ├── home/
│   │   ├── members/
│   │   ├── messages/
│   │   ├── nav/
│   │   ├── register/
│   │   ├── guards/
│   │   ├── resolvers/
│   │   └── pipes/
│   │
│   └── package.json
```

## Authentication Flow

1. User registers or logs in.
2. API validates credentials.
3. JWT token is generated and returned.
4. Client stores token.
5. Route guards protect authenticated routes.
6. Authorized API requests include JWT bearer token.

## Photo Management

Users can:

* upload profile photos
* crop uploaded photos
* set a main photo
* delete non-main photos

Images are stored using Cloudinary.

## Getting Started

### Prerequisites

Install:

* .NET Core SDK 2.2
* Node.js / npm
* Angular CLI
* SQLite (optional if using local DB)

## Running the Backend

```bash
cd MatchConnect.API
dotnet restore
dotnet run
```

Backend default URL:

```text
https://localhost:5001
```

## Running the Frontend

```bash
cd MatchConnect.Client
npm install
ng serve
```

Frontend default URL:

```text
http://localhost:4200
```

## Example API Endpoints

### Authentication

```text
POST /api/auth/register
POST /api/auth/login
```

### Users

```text
GET /api/users
GET /api/users/{id}
PUT /api/users/{id}
```

### Photos

```text
POST /api/users/{userId}/photos
POST /api/users/{userId}/photos/{id}/setMain
DELETE /api/users/{userId}/photos/{id}
```

### Messages

```text
GET /api/users/{userId}/messages
POST /api/users/{userId}/messages
```

## Future Improvements

Potential enhancements:

* real-time messaging with SignalR
* notifications
* profile matching algorithms
* advanced search/filtering
* user blocking/reporting
* upgrade to latest .NET and Angular versions

## Purpose

This project was built to practice and demonstrate:

* full-stack application architecture
* secure authentication flows
* REST API development
* frontend routing and guards
* media upload integration
* stateful client/server interactions
