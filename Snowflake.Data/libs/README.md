# Required DLLs for net471 Build

Copy the following DLLs from your application's bin directory to this `libs` folder before building.

## Required DLLs

### Framework Assembly (from GAC)
- `Microsoft.CSharp.dll` - Copy from `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Microsoft.CSharp.dll`

### Azure Assemblies (from your bin folder)
- `Azure.Core.dll`
- `Azure.Storage.Blobs.dll`
- `Azure.Storage.Common.dll`

### Google Cloud Assemblies (from your bin folder)
- `Google.Cloud.Storage.V1.dll`
- `Google.Apis.dll`
- `Google.Apis.Storage.v1.dll`
- `Google.Apis.Auth.dll`
- `Google.Apis.Core.dll`
- `Google.Api.CommonProtos.dll`
- `Google.Api.Gax.dll`
- `Google.Api.Gax.Grpc.dll`
- `Google.Api.Gax.Rest.dll`
- `Google.Protobuf.dll`

### Security/Crypto Assemblies (from your bin folder)
- `BouncyCastle.Cryptography.dll`
- `Microsoft.IdentityModel.Logging.dll`
- `Microsoft.IdentityModel.Tokens.dll`
- `System.IdentityModel.Tokens.Jwt.dll`

### Microsoft Extensions Assemblies (from your bin folder)
- `Microsoft.Bcl.AsyncInterfaces.dll`
- `Microsoft.Extensions.DependencyInjection.Abstractions.dll`
- `Microsoft.Extensions.Logging.dll`
- `Microsoft.Extensions.Logging.Abstractions.dll`
- `Microsoft.Extensions.Options.dll`
- `Microsoft.Extensions.Primitives.dll`

### JSON/Serialization Assemblies (from your bin folder)
- `Newtonsoft.Json.dll`
- `System.Text.Json.dll`
- `System.Text.Encodings.Web.dll`

### System Assemblies (from your bin folder)
- `System.Buffers.dll`
- `System.Collections.Immutable.dll`
- `System.Memory.dll`
- `System.Runtime.CompilerServices.Unsafe.dll`
- `System.Threading.Tasks.Extensions.dll`

## Build Instructions

After copying all DLLs to this folder, run from the repository root:

```powershell
# Clean and restore
dotnet restore Snowflake.Data/Snowflake.Data.csproj

# Build for net471
dotnet build Snowflake.Data/Snowflake.Data.csproj -f net471 -c Release
```

## Output

The compiled `Snowflake.Data.dll` will be in:
`Snowflake.Data/bin/Release/net471/Snowflake.Data.dll`

Copy this single DLL to your application's bin directory.

## Notes

- AWSSDK packages (AWSSDK.S3, AWSSDK.Core) come from NuGet - you don't need to copy these
- Apache.Arrow comes from NuGet - you don't need to copy this
- All other assemblies must be in your libs folder to match your application's exact versions
