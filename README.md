# Getting Started

Plea is a .NET 7 implementation of [JSend](https://github.com/omniti-labs/jsend) specification for a simple, no-frills, JSON-based format for application-level communication.

## Prerequisites

* [.NET 7 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/7.0)
* [Visual Studio 2022](https://visualstudio.microsoft.com/vs/)

## Installation

To install `Plea.AspNetCore` and its dependencies via `.NET Core CLI`, execute the following command.

```powershell
dotnet add package Plea.AspNetCore
```

To install `Plea.AspNetCore` and its dependencies via `NuGet`, execute the following command.

```powershell
Install-Package Plea.AspNetCore
```

## Basic Usage

To register `Plea.AspNetCore` and its dependencies, use the following code.

```csharp
using Carcass.Metadata.Stores.Abstracts;

services
    .AddCarcassLoggerAdapterFactory()
    .AddCarcassInMemoryMetadataStore()
    .AddCarcassAdHocMetadataAccessor()
    .AddPlea();
```

To extend the controller with Plea functionality, inherit it from `PleaController`.

```csharp
[Route("api/posts")]
public sealed class PostController : PleaController
{
    public PostController(IAdHocMetadataAccessor adHocMetadataAccessor) : base(adHocMetadataAccessor)
    {
    }
}
```

Use the following code to return the successful Plea response from the method.

```csharp
[HttpGet]
public async Task<ActionResult<IEnumerable<Post>>> GetPostsAsync(
	CancellationToken cancellationToken = default
)
{
	// ...
	return await PleaOkAsync(posts);
}
```
