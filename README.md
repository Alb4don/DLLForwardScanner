# Features

- Systematically parses every DLL in your system directories
- Extracts forwarded export tables using low-level PE analysis
- Maps the complete forwarding landscape of your Windows installation

# Prerequisites

- Windows 10/11
- .NET 6.0 or later
- Administrative privileges

# Basic Usage

- The simplest way to run a full system scan:

      dotnet run --configuration Release

- For those who prefer JSON output for automation:

      dotnet run --configuration Release -- --json

# Limitations 

- Full system scans can take several minutes on systems with thousands of DLLs.
- Not every forward to a non-KnownDLL is exploitable. We've tuned the risk assessment to minimize noise, but some manual review is always wise.
- This vulnerability and tool are specific to Windows systems.

# Security Considerations

- Creates test dlls in temp directories during validation. These are automatically cleaned up.
- This tool operates entirely offline.
