# Student-Management-System-CCP
Student Event Management System- CCP WEB ENGINEERING THEORY PROJECT 
This backend API provides comprehensive management for student events, participant registrations, and feedback submissions. Developed as the solution for the Complex Computing Problem (CCP) in the Web Engineering course of the BS (SE) program at FEST, the system offers robust functionality through an interface.

Built with ASP.NET Core 9.0 and Entity Framework Core 8.0+, the API supports both SQL Server and MySQL database systems for flexible deployment.

Core Functionality
Event Management: Full lifecycle handling of events with create, read, update, and delete operations

Participant Registration: Student enrollment system with many-to-many relationship modeling

Feedback Collection: Post-event review submission with temporal validation

Search & Filtering: Advanced query capabilities for event discovery

Data Validation: Comprehensive input checking and error handling

API Documentation: Integrated Swagger UI for interactive testing

Prerequisites
Ensure these components are installed before proceeding:

.NET 9.0 SDK

Database system: SQL Server Express or MySQL Community Server

Development environment: Visual Studio 2022 or VS Code

Git for version control operations

Configuration Guide
Clone the above repository:
cd student-event-api
Configure database connection:
Update appsettings.json with your database credentials:

json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=StudentEventDB;User Id=sa;Password=yourPassword;TrustServerCertificate=True;"
}
Apply database migrations:

bash
dotnet ef database update
Launch the application:

bash
dotnet run
API Access Points
The API will be accessible at these base URLs:

https://localhost:7121

http://localhost:5253

Interactive documentation is available at:
https://localhost:7121/swagger

Solution Architecture
The implementation follows a layered architecture pattern:

text
├── Controllers/          # API endpoint handlers
│   ├── EventsController.cs
│   ├── RegistrationsController.cs
│   └── FeedbackController.cs
│
├── Models/               # Database entity definitions
│   ├── Event.cs
│   ├── Student.cs
│   ├── Registration.cs
│   └── Feedback.cs
│
├── DTOs/                 # Data transfer objects
│   ├── EventDTO.cs
│   ├── RegistrationDTO.cs
│   └── FeedbackDTO.cs
│
├── Services/             # Business logic layer
│   ├── EventService.cs
│   ├── RegistrationService.cs
│   └── FeedbackService.cs
│
├── Data/                 # Database access layer
│   ├── AppDbContext.cs
│   └── DbInitializer.cs
│
├── Migrations/           # Database schema versioning
├── Properties/           # Runtime configuration
├── appsettings.json      # Application settings
└── Program.cs            # Startup configuration
System Features
Event Management
Create new events with comprehensive details

Retrieve upcoming events with sorting options

Modify existing event information

Remove obsolete or canceled events

Participant Registration
Enroll students in upcoming events

Prevent duplicate registrations

Track registration timestamps

Feedback Processing
Collect post-event ratings and comments

Ensure feedback is only submitted after event completion

Prevent multiple submissions for same event

Search Capabilities
Find events by name or venue

Filter results by date range

Sort listings by various criteria

Testing Endpoints
Create Event
bash
POST /api/events
Content-Type: application/json

{
  "name": "Tech Symposium",
  "description": "Annual technology conference",
  "venue": "Main Auditorium",
  "startDate": "2025-08-15T09:00:00",
  "endDate": "2025-08-16T17:00:00"
}
Register Participant
bash
POST /api/registrations
Content-Type: application/json

{
  "eventId": 1,
  "studentId": 1
}
Submit Feedback
bash
POST /api/feedback
Content-Type: application/json

{
  "eventId": 1,
  "studentId": 1,
  "rating": 4,
  "comment": "Well-organized sessions with relevant content"
}
Implementation Details
The solution addresses these complex computing requirements:

CCP Attribute	Implementation Approach
Conflicting Requirements	Balanced RESTful design with relational database constraints and real-time validation
Depth of Analysis	Comprehensive implementation of EF Core relationships and business logic
Knowledge Depth	Integration of ASP.NET Core, API design patterns, and database optimization
License
This project is licensed under the MIT License - see the LICENSE file for details.
