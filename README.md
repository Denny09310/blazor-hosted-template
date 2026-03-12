# Blazor WebAssembly Hosted Template

A custom **multi-project template** for quickly creating a solution that combines:

- **Blazor WebAssembly (standalone)** client app (`Client`)
- **ASP.NET Core Web API** backend (`Server`)
- A shared **solution file** (`.sln` or `.slnx`)
- Configurable **.NET version** (8, 9, or 10 preview)

---

## 🧰 Features

- 🔧 Ready-to-run hosted Blazor WebAssembly + Web API setup
- 🎯 Choose your target framework: `.NET 8`, `.NET 9`, or `.NET 10`
- 🧩 Choose solution format: `.sln` or `.slnx`
- ⚡ Automatically restores NuGet packages after creation
- 🖼️ Custom icon for Visual Studio / `dotnet new` list view

---

## 🚀 How to Install

### Option 1 — From Local Folder

If you cloned or downloaded this repo:

```bash
dotnet new --install ./MyBlazorHostedTemplate
````

### Option 2 — From NuGet Package (after publishing)

```bash
dotnet new --install Denny09310.AspNetCore.Blazor.Templates::<version>
```

Replace `<version>` with the NuGet version (e.g. `1.0.0`).

---

## 🧩 Create a New Project

Run one of the following commands:

```bash
# Default (uses .NET 9 and classic .sln)
dotnet new blazor-hosted -n MyApp

# Use .NET 8 (LTS)
dotnet new blazor-hosted -n MyApp -p framework=net8.0

# Use .NET 10 (preview)
dotnet new blazor-hosted -n MyApp -p framework=net10.0

# Use accelerated .slnx format
dotnet new blazor-hosted -n MyApp -p format=slnx
```

---

## 🗂️ Generated Structure

After creation, you’ll get a solution like this:

```
MyApp/
├── MyApp.sln (or MyApp.slnx)
├── Client/
│   ├── Client.csproj
│   └── (Blazor WebAssembly app)
└── Server/
    ├── Server.csproj
    └── (ASP.NET Core Web API)
```

---

## ⚙️ Template Parameters

| Parameter   | Alias           | Description                                      | Default  |
| ----------- | --------------- | ------------------------------------------------ | -------- |
| `framework` | `-p framework=` | Target framework (`net8.0`, `net9.0`, `net10.0`) | `net9.0` |
| `format`    | `-p format=`    | Solution type (`sln` or `slnx`)                  | `sln`    |

---

## 💡 Development Notes

* The icon is located in `.template.config/images/icon.png`
* Template configuration: `.template.config/template.json`
* CLI display configuration: `.template.config/dotnetcli.host.json`
* Automatically runs `dotnet restore` after creation

---

## 🧪 Testing Locally

Uninstall / reinstall after making changes:

```bash
dotnet new --uninstall ./MyBlazorHostedTemplate
dotnet new --install ./MyBlazorHostedTemplate
```

List your installed templates:

```bash
dotnet new list
```

---

## 📦 Packaging for Distribution

### Option 1 — Pack from `.nuspec`

```bash
nuget pack BlazorHostedTemplate.nuspec
dotnet new --install ./Denny09310.AspNetCore.Blazor.Templates.1.0.0.nupkg
```

### Option 2 — Pack via SDK Project

```bash
dotnet pack ./TemplatePack/TemplatePack.csproj -c Release
dotnet new --install ./bin/Release/Denny09310.AspNetCore.Blazor.Templates.1.0.0.nupkg
```

---

## 🧑‍💻 Author

**Denny09310**
📧 [k.denny2000@gmail.com](mailto:k.denny2000@gmail.com)
🗓️ Version: 1.0.0
🏷️ Identity: `dev.denny09310.blazor-hosted`

---

## 📝 License

MIT License — feel free to use and modify for your own templates.