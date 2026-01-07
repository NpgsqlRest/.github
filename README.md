# NpgsqlRest

**Transform Your PostgreSQL Database into a RESTful API Instantly**

NpgsqlRest is a modern, production-ready solution that automatically exposes your PostgreSQL database as a standalone REST API server. Generate endpoints directly from your database—tables, views, functions, and procedures—using simple comment annotations.

## 🚀 Key Features

- **Instant REST API Generation** - Automatically create RESTful endpoints from database structure and function comments
- **Declarative Configuration** - Configure API behavior directly in PostgreSQL using comments
- **TypeScript & HTTP Client Code Generation** - Automatically generate type-safe front-end fetch modules
- **Enterprise-Grade Capabilities** - Authentication, authorization, rate limiting, caching, real-time streaming (SSE), and OpenAPI support
- **Zero Dependencies** - Available as AOT-compiled executable (.NET 8/9), npm package, and Docker image
- **Production Ready** - Built for scalability and performance with minimal overhead

## 📦 Installation

### npm
```bash
npm i npgsqlrest
npx npgsqlrest
```

### Docker
```bash
docker run -p 8080:8080 -v ./appsettings.json:/app/appsettings.json vbilopav/npgsqlrest:latest
```

### .NET
```bash
dotnet add package NpgsqlRest
```

## 🎯 Quick Start

1. **Annotate your PostgreSQL functions:**
```sql
create function hello(_name text) returns text language sql as $$
  select 'Hello, ' || _name
$$;
comment on function hello(text) is 'HTTP GET /hello';
```

2. **Configure your connection** (appsettings.json):
```json
{
  "ConnectionStrings": {
    "Default": "Host=localhost;Port=5432;Database=my_db;Username=postgres;Password=postgres"
  }
}
```

3. **Run the server** and access your API at `http://localhost:8080/hello?name=World`

## 📚 Documentation & Resources

- **Documentation** - [npgsqlrest.github.io](https://npgsqlrest.github.io/)
- **Main Repository** - [NpgsqlRest/NpgsqlRest](https://github.com/NpgsqlRest/NpgsqlRest)
- **Example Project** - [NpgsqlRestTodo](https://github.com/NpgsqlRest/NpgsqlRestTodo)
- **NuGet Package** - [NpgsqlRest on NuGet](https://www.nuget.org/packages/NpgsqlRest/)

## 💡 Why NpgsqlRest?

- **Rapid Development** - Dramatically reduce time to expose your PostgreSQL as a REST API
- **Database-First Approach** - All endpoint definitions, security, and formatting managed from your database
- **Type Safety** - Generate type-safe TypeScript clients automatically
- **Perfect For** - Rapid prototyping, code generation, and scalable enterprise APIs

## 🎓 Requirements

- PostgreSQL 13 or higher
- .NET 8 or 9 (for .NET usage)
- Node.js (for npm usage)

---

**Get started today and transform your PostgreSQL database into a powerful REST API! ⚡**