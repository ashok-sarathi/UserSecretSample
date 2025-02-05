# UserSecretSample

```sh
dotnet user-secrets init
dotnet user-secrets set "ConnectionString:LocalDb" "testconnectionstring"
dotnet user-secrets set "ConnectionString:TestDb" "testconnectionstring"
dotnet user-secrets remove "ConnectionString:TestDb"
```

```cs
var builder = WebApplication.CreateBuilder(args);
app.MapGet("/sample", (IConfiguration configuration) =>
{
    return configuration.GetSection("ConnectionString:LocalDb").Value;
});
app.Run();
```
