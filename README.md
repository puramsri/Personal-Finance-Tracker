# Personal Finance Tracker

## 📌 Overview
A **Personal Finance Tracker** built using **.NET Core**, **Angular/React**, and **SQL Server** to help users manage their income, expenses, and savings efficiently. This project demonstrates **backend API development, front-end integration, database management, and CI/CD automation**.

---

## 🚀 Tech Stack
### **Backend (ASP.NET Core API)**
- **.NET 6/8, C#**
- **Entity Framework Core** (Code-first approach)
- **JWT Authentication**
- **Repository Pattern & Dependency Injection**
- **Swagger for API Documentation**
- **API Versioning**
- **Logging with Serilog**
- **Health Checks & Monitoring**
- **Performance Monitoring with Application Insights**

### **Frontend (Angular/React)**
- **Angular 15+ / React 18+**
- **Bootstrap / Tailwind CSS** for UI styling
- **State Management (NgRx / Redux)**
- **API Integration using Axios/HttpClient**
- **Jest / React Testing Library for Unit Tests**

### **Database (SQL Server)**
- **Tables:** Users, Transactions, Categories
- **Stored Procedures & Indexing**
- **Migrations using EF Core**

### **DevOps & CI/CD**
- **Azure DevOps / GitHub Actions** for automated builds & deployments
- **Docker** for containerized deployment
- **Unit & Integration Tests** using **xUnit & Moq** (Backend)
- **Frontend Unit Tests using Jest & React Testing Library**
- **Hosting:** Azure App Service / AWS Lambda (Optional)

---

## 📂 Folder Structure
```
📂 PersonalFinanceTracker
│── 📂 Backend (.NET Core API)
│   │── Controllers/
│   │── Services/
│   │── Models/
│   │── Data/
│   │── Repositories/
│   │── UnitTests/
│   │── Program.cs
│   │── Startup.cs
│   │── appsettings.json
│   │── Swagger/
│   │── Logging/
│   │── Versioning/
│   │── HealthChecks/
│   │── Monitoring/
│
│── 📂 Frontend (Angular or React)
│   │── src/components/
│   │── src/pages/
│   │── src/services/
│   │── src/tests/
│   │── src/app.tsx / main.ts
│   │── package.json
│   │── tsconfig.json
│
│── 📂 Database (SQL Scripts)
│   │── schema.sql
│   │── seed-data.sql
│   │── migrations/
│
│── 📂 CI/CD (Azure DevOps or GitHub Actions)
│   │── azure-pipelines.yml
│   │── .github/workflows/build.yml
│
│── 📂 Docker
│   │── Dockerfile
│   │── docker-compose.yml
│
│── 📂 API Documentation
│   │── PostmanCollection.json
│
│── README.md (Project Overview)
│── LICENSE (MIT)
│── CONTRIBUTING.md (For open-source contributions)
│── .gitignore
```

---

## ✅ Features
- **User Authentication & Authorization** (JWT-based login/signup)
- **CRUD Operations** for **Income, Expenses, Categories**
- **Dashboard** with Charts & Insights
- **Search & Filter Transactions**
- **Responsive UI for Mobile & Web**
- **Automated CI/CD Deployment**
- **Containerized with Docker**
- **Unit & Integration Tests with xUnit & Moq** (Backend)
- **Database Migrations using EF Core**
- **Frontend Unit Tests with Jest & React Testing Library**
- **API Documentation with Swagger & Postman Collection**
- **API Versioning Implementation**
- **Logging with Serilog**
- **Health Checks & Monitoring**
- **Performance Monitoring with Application Insights**

---

## 🛠️ Setup & Installation
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/yourusername/PersonalFinanceTracker.git
cd PersonalFinanceTracker
```

### **2️⃣ Backend Setup (.NET API)**
```bash
cd Backend
# Restore Dependencies
dotnet restore
# Run Migrations
dotnet ef migrations add InitialCreate
dotnet ef database update
# Run API
dotnet run
```

#### **Enable Performance Monitoring with Application Insights (Startup.cs)**
```csharp
using Microsoft.OpenApi.Models;
using Microsoft.AspNetCore.Mvc;
using Microsoft.ApplicationInsights.Extensibility;
using Serilog;

var builder = WebApplication.CreateBuilder(args);

// Configure Application Insights
builder.Services.AddApplicationInsightsTelemetry();

// Configure Serilog
Log.Logger = new LoggerConfiguration()
    .WriteTo.Console()
    .WriteTo.File("logs/log-.txt", rollingInterval: RollingInterval.Day)
    .CreateLogger();

builder.Host.UseSerilog();

builder.Services.AddControllers();
builder.Services.AddHealthChecks();
builder.Services.AddApiVersioning(o =>
{
    o.AssumeDefaultVersionWhenUnspecified = true;
    o.DefaultApiVersion = new ApiVersion(1, 0);
    o.ReportApiVersions = true;
});
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen(c =>
{
    c.SwaggerDoc("v1", new OpenApiInfo { Title = "Finance API", Version = "v1" });
});

var app = builder.Build();
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI(c => c.SwaggerEndpoint("/swagger/v1/swagger.json", "Finance API v1"));
}

app.UseSerilogRequestLogging();
app.UseAuthorization();
app.MapHealthChecks("/health");
app.MapControllers();
app.Run();
```

### **3️⃣ Frontend Setup (Angular/React)**
```bash
cd Frontend
# Install dependencies
npm install
# Run unit tests
npm test
# Start the app
npm start
```

### **4️⃣ Docker Setup (Optional for Deployment)**
```bash
# Build and run the application using Docker
docker-compose up --build
```

---

## 📜 License
This project is licensed under the **MIT License**.

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 🌟 Acknowledgments
Thanks to the open-source community for inspiration and tools to make this project possible!

---

🔗 **GitHub Repository:** https://github.com/puramsri/Personal-Finance-Tracker
![image](https://github.com/user-attachments/assets/e6f63b60-dbdf-470b-9dc1-726fad62d37d)
