# Required DLLs for net471 Build

Copy the following DLLs from your application's bin directory to this `libs` folder before building.

## Required DLLs (copy from your application's bin directory)

### Framework Assembly (from GAC)
- `Microsoft.CSharp.dll` - Copy from `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Microsoft.CSharp.dll`

### AWS SDK Assemblies (download from NuGet)
These are NOT in your existing app - download from NuGet:
1. Download `AWSSDK.S3` 4.0.4 from https://www.nuget.org/packages/AWSSDK.S3/4.0.4
2. Download `AWSSDK.Core` 4.0.0.14 from https://www.nuget.org/packages/AWSSDK.Core/4.0.0.14
3. Extract the .nupkg files (rename to .zip), find the DLLs under `lib\netstandard2.0\`:
   - `AWSSDK.S3.dll`
   - `AWSSDK.Core.dll`

### Azure Assemblies
- `Azure.Core.dll` (version 1.19.0.0)
- `Azure.Storage.Blobs.dll`
- `Azure.Storage.Common.dll`

### Google Cloud Assemblies
- `Google.Cloud.Storage.V1.dll`
- `Google.Apis.dll`
- `Google.Apis.Storage.v1.dll`
- `Google.Apis.Auth.dll`
- `Google.Apis.Core.dll`
- `Google.Api.CommonProtos.dll`
- `Google.Api.Gax.dll`
- `Google.Api.Gax.Grpc.dll`
- `Google.Api.Gax.Rest.dll`
- `Google.Protobuf.dll` (version 3.28.2.0)

### Security/Crypto Assemblies
- `BouncyCastle.Cryptography.dll`
- `Microsoft.IdentityModel.Logging.dll`
- `Microsoft.IdentityModel.Tokens.dll`
- `System.IdentityModel.Tokens.Jwt.dll`

### Microsoft Extensions Assemblies
- `Microsoft.Bcl.AsyncInterfaces.dll` (version 7.0.0.0)
- `Microsoft.Extensions.DependencyInjection.Abstractions.dll`
- `Microsoft.Extensions.Logging.dll`
- `Microsoft.Extensions.Logging.Abstractions.dll` (version 6.0.0.1)
- `Microsoft.Extensions.Options.dll`
- `Microsoft.Extensions.Primitives.dll`

### JSON/Serialization Assemblies
- `Newtonsoft.Json.dll` (version 13.0.0.0)
- `System.Text.Json.dll` (version 8.0.0.5)
- `System.Text.Encodings.Web.dll` (version 7.0.0.0)

### System Assemblies
- `System.Buffers.dll` (version 4.0.3.0)
- `System.Collections.Immutable.dll` (version 7.0.0.0)
- `System.Memory.dll` (version 4.0.1.2)
- `System.Runtime.CompilerServices.Unsafe.dll` (version 6.0.0.0)
- `System.Threading.Tasks.Extensions.dll` (version 4.2.0.1)

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
