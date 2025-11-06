# Understanding .NET

- [Understanding .NET](#understanding-net)
  - [.NET Support](#net-support)
    - [Support Phases](#support-phases)
  - [Understanding intermediate language](#understanding-intermediate-language)
  - [Commands](#commands)

## .NET Support

- **LTS : Long Term Support**
  - 3 years supported by Microsoft after General Availability (GA)
  - or 1 year after the next LTS release ships
- **STS : Standard Term Support (Current)**
  - release may change based on feedback
  - supported by Microsoft for 18 months after GA
  - or 6 months after the next STS or LTS release ships
- **Preview**
  - public testing release
  - good for programming book authors who need to have early access to new language features, libraries and app& service platforms

### Support Phases

- Preview : This are not supported at all
- Go Live : These are supported until GA, then become immediately unsupported.
- Active : .NET 9 will be in this support phase from November 2024 to November 2025.
- Maintenance : Supported only with security fixes for the last 6 months of its lifetime. .NET 9 will be in this support phase from November 2025 to May 2026.
- EOL: Not supported. .NET 9 will reach its EOL in May 2026.
  - **End of support** or **end of life (EOL)** means the date after which bug fixes, security updates, or technical assistance are no longer available from Microsoft.

---

## Understanding intermediate language

- The C# compiler (Roslyn) used by the _dotnet_ CLI tool converts C# source code into **intermediate language (IL)** code.
- Stores the **IL** in an **assembly (DLL or EXE file.)**.
- **IL** code statements are like assembly language instructions, which are executed by **.NET’s virtual machine**, known as **CoreCLR**, the newer name for the **Common Language Runtime (CLR)** in modern .NET.
- At runtime, **CoreCLR** loads the **IL** code from the **assembly**, the **just-in-time (JIT)** compiler compiles it into native CPU instructions and then it is executed by the CPU on your machine.
- The benefit of this two-step compilation process is that Microsoft can create CLRs for Linux and macOS, as well as for Windows. The same IL code runs everywhere because of the second compilation step, which generates code for the native operating system and CPU instruction set.

> Compilation process typically translating source code into IL, which is then compiled into machine code at runtime by the CLR using JIT compilation.

## Commands

1. Create a folder for the solution : `mkdir <solution_folder_name>`
2. Change to the folder : `cd <solution_folder_name>`
3. Create a solution file in the folder : `dotnet new sln`
4. Create a folder and project using a template : `dotnet new console -o <project_folder_name>`
5. Add the folder and its project to the solution : `dotnet sln add <project_folder_name>`
6. Create a folder and project using template with specific .net version : `dont new console -o <project_folder_name> -f net8.0`
