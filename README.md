# 📖 Book Web Store
📚 ASP.NET Core project developed as part of the [*C# Web - June 2025 @ SoftUni*](https://softuni.bg/trainings/4954/asp-net-advanced-june-2025) course.

Welcome to **BookWebStore** – an online bookstore web application built with ASP.NET Core MVC, demonstrating authentication, authorization, database management, and e-commerce functionality.

---

## ✨ Features
- 🔐 User registration and login (ASP.NET Identity)
- 🔍 Search across books, genres, and authors
- 🛒 Shopping cart with a dynamic book count
- ✍️ Blog section with role-based permissions
- ⭐ Book ratings and reviews
- 📦 Order creation and management

---

## 👥 Roles & Permissions

### User Roles
- **Guest**: All newly registered users are assigned the Guest role by default. Can write and edit reviews, and place orders.  
- **Moderator**: Can edit certain fields of Books and Blogs. Can also write reviews and place orders.  
- **Administrator**: Can create Genres, Authors, Books, and Blogs. Can edit and delete Blogs and Books. Can also write reviews and place orders.  
- **Master Admin (kontakta39)**: Has all administrator privileges. Can additionally change roles of other users. Stored in the database as an Administrator.  

---

### Blog Permissions

| Role                  | Create | Edit | Delete |
|-----------------------|--------|------|--------|
| Master Admin          | ✅      | ✅    | ✅      |
| Administrator (Owner) | ✅      | ✅    | ✅      |
| Administrator (Not Owner) | ❌      | ❌    | ❌      |
| Moderator             | ❌      | ✅    | ❌      |
| Guest                 | ❌      | ❌    | ❌      |

---

### Summary of Actions by Role

| Action                                  | Guest | Moderator | Administrator | Master Admin |
|----------------------------------------|-------|-----------|---------------|--------------|
| Write & Edit Reviews                    | ✅    | ✅        | ✅            | ✅           |
| Place Orders                            | ✅    | ✅        | ✅            | ✅           |
| Create Genres, Authors, Books, Blogs   | ❌    | ❌        | ✅            | ✅           |
| Edit Books (some fields)                | ❌    | ✅        | ✅            | ✅           |
| Edit Blogs (some fields)                | ❌    | ✅        | ✅            | ✅           |
| Delete Blogs                            | ❌    | ❌        | ✅            | ✅           |
| Change User Roles                        | ❌    | ❌        | ❌            | ✅           |

---

## 🛠️ Technologies Used

### Backend
- **ASP.NET Core MVC**: Robust and scalable web framework.  
- **Entity Framework Core**: Efficient database interactions using LINQ and migrations.  
- **SQL Server**: Relational database used for storing all application data.  
- **ASP.NET Identity**: Secure authentication and authorization system using **custom ApplicationUser and ApplicationRole classes**. Business logic for user and role operations is implemented manually, not scaffolded.  

### Frontend
- **Bootstrap 5**: Responsive and modern UI components.

### Testing
- **NUnit**: Unit testing framework.  
- **Moq**: Mocking framework for unit testing.

---

## 🛠️ Requirements

- .NET 10 SDK
- SQL Server (Express / Developer)
- Git

---

## 🚀 How to Clone and Run the Project

**1. Clone the repository**
```bash
git clone https://github.com/kontakta39/BookWebStore-ASP.NET-Core.git
cd BookWebStore-ASP.NET-Core
```

**2. Set the connection string locally using user secrets:**

Replace (PC_NAME) with your local SQL Server instance name.

```bash
dotnet user-secrets set "ConnectionStrings:BookStoreConnectionString" "Server=(PC_NAME)\SQLEXPRESS;Database=BookStoreDb;Trusted_Connection=True;TrustServerCertificate=True;"
```

**3. Restore dependencies, apply migrations, and run:**
```bash
dotnet restore
dotnet run
```

**4. Open in your browser:**
```bash
https://localhost:7031
```

---

## 🔑 Default Admin Account

**Note:** By default, the project comes with a pre-configured administrator account for local development and testing:

- **Username:** Admin
- **Email:** admin@example.com
- **Password:** Admin123!

⚠️ These credentials are intended only for local development and testing purposes.

---

## 📜 License

This project is licensed under the MIT License. See the [*LICENSE*](LICENSE) file for details.

---

Enjoy exploring the BookWebStore project! 📖🛒
