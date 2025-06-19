# Student-Management-System-CCP
Student Event Management System- CCP WEB ENGINEERING THEORY PROJECT 
This backend API provides comprehensive management for student events, participant registrations, and feedback submissions. Developed as the solution for the Complex Computing Problem (CCP) in the Web Engineering course of the BS (SE) program at FEST, the system offers robust functionality through an interface.

Built with ASP.NET Core 9.0 and Entity Framework Core 8.0+, the API supports both SQL Server and MySQL database systems for flexible deployment.

# Key Features Implemented
📌 Full CRUD (Create, Read, Update, Delete) operations for Events.
📌 Participant registration for events, modeling a many-to-many relationship.
📌 Feedback submission (rating and comment) for events, restricted to after the event date.
📌 Event searching by name or venue.
📌 Event filtering by date or venue, and sorting capabilities.
📌 Input validation and standardized HTTP error handling for API responses.
📌 Swagger UI integration for interactive API documentation and testing.

# Prerequisites
📌 Ensure these components are installed before proceeding:

📌 .NET 9.0 SDK

📌 Database system: SQL Server Express or MySQL Community Server

📌 Development environment: Visual Studio 2022 or VS Code

# 📝 Configuration Guide
1. Clone the repository:[ Git for version control operations]
https://github.com/Atiq-Developer/Student-Management-System-CCP.git
cd student-event-api
2. Configure database connection:
Update appsettings.json with your database credentials:
json
"ConnectionStrings": {
        "DefaultConnection": "Server=03413812449\\SQLEXPRESS02;Database=StudentEventDb;Trusted_Connection=True;MultipleActiveResultSets=true;Encrypt=False"
    }
3. Apply database migrations:
dotnet ef database update
4. Launch the application:
dotnet run

# API Access Points
The API will be accessible at these base URLs:
https://localhost:7121
http://localhost:5253

Interactive documentation is available at:
https://localhost:7121/swagger

# Project Structure
The solution follows a layered architecture to ensure separation of concerns:

- /Controllers: Contains API controllers (e.g., EventsController.cs) that handle incoming HTTP requests and route them to appropriate services.
- /Models (or /Entities): Houses the EF Core domain entity classes (e.g., Event.cs, Student.cs) that represent the database tables.
- /DTOs: Includes Data Transfer Objects used to shape data for API requests and responses, aiding in validation and API contract definition.
- /Services: Contains the business logic layer (e.g., EventService.cs), orchestrating operations between controllers and data access.
- /Data: Holds the ApplicationDbContext.cs for Entity Framework Core configurations and database interaction.
- /Migrations: Stores EF Core generated database migration files detailing schema changes.
- Program.cs: The main entry point for the application, responsible for configuring services and the HTTP request pipeline.
- appsettings.json: Contains application configuration settings, including database connection strings.


# CCP Attribute	Implementation Approach
- Conflicting Requirements	Balanced  design with relational database constraints and real-time validation
- Depth of Analysis	Comprehensive implementation of EF Core relationships and business logic
- Knowledge Depth	Integration of ASP.NET Core, API design patterns, and database optimization
# License
This project is licensed under the MIT License - see the LICENSE file for details.
