# Eduflix

**Eduflix** is an online course platform built with ASP.NET Core. It allows users to register, create and manage educational content, purchase courses, and access exclusive video lessons.

---

## Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Installation & Run](#installation--run)
- [Database Configuration](#database-configuration)
- [Technologies Used](#technologies-used)
- [Routing Overview](#routing-overview)
- [To-Do](#to-do)
- [License](#license)

---

## About the Project

Eduflix is an LMS (Learning Management System) designed for course creators and learners. It supports uploading episodes, purchasing courses using wallet balance, and provides both user and admin panels for management.

---

## Features

- ASP.NET Identity-based authentication
- Admin dashboard via Areas
- Course and episode creation
- Wallet system with discount support
- Purchase history tracking
- Category-based filtering
- Responsive UI with Razor Views

---

## Architecture

The project is split into three main layers:

- `TopLearn.Core`: Contains core models, interfaces, and view models.
- `TopLearn.DataLayer`: Implements EF Core, database context, and repositories.
- `TopLearn.Web`: The presentation layer using MVC and Razor Views.

---

## Prerequisites

- [.NET 6 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
- SQL Server
- Visual Studio 2022 or JetBrains Rider

---

## Installation & Run

### 1. Clone the Repository

```bash
git clone https://github.com/mahdizargarzadeh/Eduflix.git
```

### 2. Open the Solution

Open `OnlineCourse.sln` in Visual Studio.

### 3. Configure the Startup Project

Right-click on the `TopLearn.Web` project and select **Set as Startup Project**.

### 4. Apply Database Migrations

Open **Package Manager Console** and run:

```powershell
Update-Database
```

This command will create the database and apply all migrations using EF Core.

### 5. Run the Project

Press `F5` or `Ctrl + F5` to build and launch the website.

---

## Database Configuration

Open the `appsettings.json` file in the `TopLearn.Web` project and update the connection string:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=Eduflix_DB;Trusted_Connection=True;MultipleActiveResultSets=true"
}
```

- For a named SQL instance, replace `Server=.` with something like `Server=localhost\SQLEXPRESS`.
- If using SQL authentication:

```json
"DefaultConnection": "Server=localhost;Database=Eduflix_DB;User Id=sa;Password=YourPassword;"
```

Make sure SQL Server is running and accessible.

---

## Technologies Used

- ASP.NET Core MVC
- Entity Framework Core
- Razor View Engine
- SQL Server
- Bootstrap 4
- ASP.NET Identity
- CKEditor
- Custom Middleware / Filters

---

## Routing Overview

- `/`: Home page
- `/Course/ShowCourse/{id}`: Course detail view
- `/UserPanel`: User dashboard
- `/Admin`: Admin dashboard (users, courses, discounts, etc.)

---

## To-Do

- Integrate real payment gateways
- Add email verification for new users
- Implement comments and course rating system
- Improve search (AJAX-based)
- Add analytics & reporting dashboard

---

## License

This project is licensed under the [MIT License](LICENSE).

---

> Created with love by **Mahdi Zargarzadeh**
