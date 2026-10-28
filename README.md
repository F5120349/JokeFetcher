# 🎭 Joke Fetcher

A small C# console application developed as part of a university programming lab to practise working with **REST APIs, HTTP requests and JSON deserialization**.

The application connects to the **Official Joke API**, retrieves jokes from different endpoints and displays them in the console.

## 📌 Project Overview

The application demonstrates how a C# program can communicate with an external web service and process the JSON data returned by the API.

It retrieves:

- 🎭 A single random joke
- 😂 A collection of 10 random jokes
- 💻 10 programming jokes

The returned JSON is deserialized into C# objects before being displayed in the console.

## 🛠️ Technologies & Tools

- **C#**
- **.NET 10**
- **HttpClient**
- **REST API**
- **JSON**
- **System.Text.Json**

## 🧠 Key Concepts Demonstrated

This project demonstrates practical experience with:

- Making HTTP `GET` requests
- Working with REST API endpoints
- Using `HttpClient`
- Handling HTTP responses
- Deserializing JSON into C# objects
- Using DTOs
- Working with `List<T>`
- Iterating through collections
- Basic exception handling
- Checking for unsuccessful HTTP responses
- Creating reusable methods

## 🌐 API Integration

The application uses the **Official Joke API**.

The base API URL is:

```text
https://official-joke-api.appspot.com/
```

The application interacts with the following endpoints:

| Endpoint | Purpose |
| --- | --- |
| `jokes/random` | Retrieves a single random joke |
| `jokes/ten` | Retrieves 10 random jokes |
| `jokes/programming/ten` | Retrieves 10 programming jokes |

## 📦 Data Model

The API response is mapped to a simple `Joke` DTO containing:

```csharp
public class Joke
{
    public string Setup { get; set; } = string.Empty;
    public string Punchline { get; set; } = string.Empty;
}
```

This allows the JSON response to be converted into strongly typed C# objects.

## 🔄 JSON Deserialization

The project uses `System.Text.Json` to convert the API responses into C# objects.

Case-insensitive property matching is enabled so that the JSON property names can be mapped to the C# properties:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true
};
```

## ⚠️ Error Handling

HTTP requests are wrapped in `try-catch` blocks to handle `HttpRequestException` errors.

The application also uses:

```csharp
response.EnsureSuccessStatusCode();
```

to ensure unsuccessful HTTP responses are handled as errors.

## 📁 Project Structure

```text
JokeFetcher/
│
├── Dtos/
│   └── Joke.cs
│
├── Program.cs
├── JokeFetcher.csproj
├── JokeFetcher.slnx
├── .gitignore
└── .gitattributes
```

## 🚀 How to Run

### Prerequisites

You will need:

- [.NET 10 SDK](https://dotnet.microsoft.com/)

### Run the Application

1. Clone the repository.

2. Open the project in Visual Studio, VS Code or another C# development environment.

3. Restore the project dependencies:

```bash
dotnet restore
```

4. Build the project:

```bash
dotnet build
```

5. Run the application:

```bash
dotnet run
```

The application will connect to the API and display the retrieved jokes in the console.

## 🎯 Project Purpose

This project was created as part of university lab work to develop practical experience with **C# and external web services**.

It provided hands-on practice with making API requests, processing JSON responses and working with strongly typed C# objects.

## 📚 Skills Practised

- C#
- REST APIs
- HTTP requests
- `HttpClient`
- JSON deserialization
- DTOs
- Exception handling
- Collections
- Console applications
