# awesome-analyzers

A curated list of .NET Compiler Platform ("Roslyn") diagnostic analyzers, code fixes, and other related resources.
Everyone can contribute here!

## Getting Started

Resources for creating your first analyzer:

* [Use Roslyn to Write a Live Code Analyzer for Your API](https://msdn.microsoft.com/en-us/magazine/dn879356.aspx) - MSDN Magazine by Alex Turner
* [Adding a Code Fix to Your Roslyn Analyzer](https://msdn.microsoft.com/en-us/magazine/dn904670.aspx) - MSDN Magazine by Alex Turner
* [How To Write a C# Analyzer and Code Fix](https://learn.microsoft.com/en-us/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix) - Microsoft Learn tutorial
* [ASP.NET Core middleware with Roslyn Analyzers](https://blog.elmah.io/asp-net-core-middleware-with-roslyn-analyzers-part-1/) - elmah.io blog by Thomas Ardal
* [.NET Analyzers GitHub organization](https://github.com/DotNetAnalyzers) - An organization for the development of analyzers (diagnostics, code fixes, and refactorings) using the .NET Compiler Platform.

## Central Package Management

If you're using [Central Package Management](https://learn.microsoft.com/en-us/nuget/consume-packages/Central-Package-Management), you can add most of the analyzers presented here as a [`GlobalPackageReference`](https://learn.microsoft.com/en-us/nuget/consume-packages/Central-Package-Management#global-package-references) in your `Directory.Packages.props` file. This applies the analyzer to all projects in the repository.

```xml
  <ItemGroup>
    <GlobalPackageReference Include="{AnalyzerNuGet}" Version="{LatestVersion}" />
  </ItemGroup>
```

## Popular Analyzers

### Analyzer collections

* [.NET source code analysis](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/overview) - Official Roslyn diagnostic analyzers developed and maintained by the Roslyn team. Built-in analyzers are included in the .NET SDK and can be enabled in your project by adding the `EnableNETAnalyzers` property to your project file. Additional analyzers are available as separate NuGet packages, such as:
  * [Microsoft.CodeAnalysis.PublicApiAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.PublicApiAnalyzers/) - A set of Roslyn diagnostic analyzers that help tracking reusable code public API exposure, aids in proper encapsulation.
  * [Microsoft.CodeAnalysis.BannedApiAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.BannedApiAnalyzers/) - A set of Roslyn diagnostic analyzers that help enforce banned APIs.
* [StyleCopAnalyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) - An implementation of StyleCop rules using the .NET Compiler Platform
* [Wintellect.Analyzers](https://github.com/Wintellect/Wintellect.Analyzers) - .NET Compiler Platform ("Roslyn") diagnostic analyzers and code fixes written by Wintellect
* [sonarlint-vs](https://github.com/SonarSource/sonarlint-visualstudio) - SonarLint is a Visual Studio 2015 extension that provides on-the-fly feedback to developers on new bugs and quality issues injected into C# code.
  * [sonar-dotnet](https://github.com/SonarSource/sonar-dotnet) - the Sonar Roslyn analyzers which are powering SonarLint. They are also published as [SonarAnalyzer.CSharp](https://www.nuget.org/packages/SonarAnalyzer.CSharp/) NuGet package.
* [Roslynator](https://github.com/JosefPihrt/Roslynator) - A collection of 500+ analyzers, refactorings and fixes for C#, powered by Roslyn.
* [ErrorProne.NET](https://github.com/SergeyTeplyakov/ErrorProne.NET) - ErrorProne.NET is a set of Roslyn-based analyzers that will help you to write correct code. The idea is similar to Google's error-prone but focusing on correctness (and, maybe, performance) of C# programs.
* [Gu.Analyzers](https://github.com/GuOrg/Gu.Analyzers) - Roslyn analyzers and fixes.
* [Meziantou.Analyzer](https://github.com/meziantou/Meziantou.Analyzer) - A Roslyn analyzer to enforce some good practices in C#.
* [SharpSource](https://github.com/Vannevelj/SharpSource) - A collection of analyzers that aim to surface defects at compile that would otherwise go unnoticed until it's too late.
* [BlowinCleanCode](https://github.com/blowin/BlowinCleanCode/) - BlowinCleanCode is a Roslyn-based C# code analyzer that aims to provide a set of rules that helps to simplify code and make it cleaner.
* [Selectorlyzer.Analyzers](https://github.com/rlgnak/Selectorlyzer.Analyzers) - Selectorlyzer.Analyzers is a highly customizable Roslyn Analyzer designed to empower developers with the ability to create project-specific analyzers using a CSS selector-like syntax.
* [Menees.Analyzers](https://github.com/menees/Analyzers) - Roslyn-based C# code analyzers. Various analyzers ported from StyleCop+.
* [Exceptionator](https://github.com/elmahio/Exceptionator) - Roslyn analyzers for improving exception handling in C# code.
* [Philips.CodeAnalysis](https://github.com/philips-software/roslyn-analyzers) - Philips Software Roslyn Diagnostic Analyzers. Contains:
  * `Philips.CodeAnalysis.DuplicateCodeAnalyzer`
  * `Philips.CodeAnalysis.MaintainabilityAnalyzers`
  * `Philips.CodeAnalysis.MoqAnalyzers`
  * `Philips.CodeAnalysis.SecurityAnalyzers`
* [AgodaAnalyzers](https://github.com/agoda-com/AgodaAnalyzers) - A set of opinionated Roslyn analyzers for C#.

### Security

* [SecurityCodeScan](https://github.com/security-code-scan/security-code-scan) - Vulnerability Patterns Detector for C# and VB.NET.
* [Puma Scan](https://www.pumascan.com) - Security analyzer that provides real time, continuous source code analysis for C# applications.

### ASP.NET Core and web

* [AspNetCoreAnalyzers](https://www.nuget.org/packages/AspNetCoreAnalyzers) - Analyzers for Microsoft.AspNetCore.

### Async/multithreading

* [AsyncFixer](https://github.com/semihokur/AsyncFixer) - Advanced Async/Await Diagnostics and CodeFixes for C#.
* [SmartAnalyzers.MultithreadingAnalyzer](https://github.com/cezarypiatek/MultithreadingAnalyzer) - A set of Roslyn analyzers related to multithreading
* [Asyncify](https://www.nuget.org/packages/Asyncify/) - Asyncify-CSharp is an analyzer and codefix that allows you to quickly update your code to use the Task Asynchronous Programming model. This model, introduced in C# 5, adds an intuitive way of handling asynchronous calls within C#. The analyzer allows large codebases to be easily modified to use the TAP model by finding violations and applying fixes up the call tree.
* [Microsoft.VisualStudio.Threading.Analyzers / vs-threading](https://www.nuget.org/packages/Microsoft.VisualStudio.Threading.Analyzers) - Static code analyzer to detect common mistakes or potential issues regarding threading and async coding.
* [DbContextThreadSafety.Analyzer](https://github.com/Maxofpower/DbContextThreadSafetyAnalyzer) - This analyzer is especially useful when working with DbContext in multi-threaded or parallel scenarios, Raising warning on misusing DbContext.

### Project file

* [.NET project file analyzers](https://github.com/dotnet-project-file-analyzers/dotnet-project-file-analyzers) - Report issues on .NET project files.
* [Reference Trimmer](https://github.com/dfederm/ReferenceTrimmer) - Easily identify which dependencies can be removed from a .NET project

### 3rd party libraries

* [Moq.Analyzers](https://github.com/rjmurillo/moq.analyzers) - Roslyn analyzer that helps to write unit tests using Moq mocking library by highlighting typical errors and suggesting quick fixes. Port of Resharper extension to Roslyn. Find the full list of detected issues at project GitHub page.
* [Roslynator.Testing.CSharp.Xunit](https://www.nuget.org/packages/Roslynator.Testing.CSharp.Xunit/) - Testing framework for Roslyn analyzers, refactorings and code fixes.
* [xunit.analyzers](https://github.com/xunit/xunit.analyzers) - Code Analyzers for projects using xUnit.net that help find and fix frequent issues when writing tests.
* [ClosedTypeHierarchyDiagnosticSuppressor](https://github.com/shuebner/ClosedTypeHierarchyDiagnosticSuppressor) - Roslyn-based C# diagnostic suppressor that enhances the `switch` exhaustiveness checks for the closed type hierarchy pattern aka discriminated unions.
* [OneOfDiagnosticSuppressor](https://github.com/shuebner/OneOfDiagnosticSuppressor) - Roslyn-based C# diagnostic suppressor that enhances the `switch` exhaustiveness checks of `OneOf<...>.Value` from the [OneOf library](https://github.com/mcintyre321/OneOf) and thus enables effective use of native `switch` as an alternative to the library's own `Switch` and `Match` methods.
* [NSubstitute.Analyzers](https://github.com/nsubstitute/NSubstitute.Analyzers) - Provides diagnostic analyzers to warn about incorrect usage of [NSubstitute](https://github.com/nsubstitute/NSubstitute) in C# or VB.
* [System.IO.Abstractions.Analyzers](https://github.com/TestableIO/System.IO.Abstractions.Analyzers) - Analyzer for helping using package [System.IO.Abstractions](https://github.com/Testably/Testably.Abstractions).
* [FluentAssertions.Analyzers](https://github.com/fluentassertions/fluentassertions.analyzers) - Analyzers based on the [FluentAssertions](https://github.com/fluentassertions/fluentassertions) best practices docs.
* [SerilogAnalyzer](https://github.com/Suchiman/SerilogAnalyzer) - Roslyn-based analysis for code using the [Serilog logging library](https://github.com/serilog/serilog). Checks for common mistakes and usage problems.

### Miscellaneous

* [NetFabric.Hyperlinq.Analyzer](https://github.com/NetFabric/NetFabric.Hyperlinq.Analyzer) - Best practices for collection enumeration in C#.
* [SmartAnalyzers.ExceptionAnalyzer](https://github.com/smartanalyzers/ExceptionAnalyzer) - A set of Roslyn analyzers related to exceptions usages.
* [DotNetAnalyzers.DocumentationAnalyzers](https://github.com/DotNetAnalyzers/DocumentationAnalyzers) - An implementation of .NET documentation rules using Roslyn analyzers and code fixes.
* [IDisposableAnalyzers](https://github.com/DotNetAnalyzers/IDisposableAnalyzers) - Analyzers and fixes for IDisposable.

## Deprecated Analyzers

* [Code Cracker](https://github.com/code-cracker/code-cracker) - An analyzer library for C# and VB that uses Roslyn to produce refactorings, code analysis, and other niceties
* [CSharpEssentials](https://github.com/DustinCampbell/CSharpEssentials) - C# Essentials is a collection of Roslyn diagnostic analyzers, code fixes and refactorings that make it easy to work with C# 6 language features.
* [RefactoringEssentials](https://github.com/icsharpcode/RefactoringEssentials/) - Free Visual Studio 2015 extension for C# and VB.NET refactorings, including code best practice analyzers to improve your projects.
* [Public API analyzer](https://github.com/DotNetAnalyzers/PublicApiAnalyzer) (Superseded by [Microsoft.CodeAnalysis.PublicApiAnalyzers](https://github.com/dotnet/roslyn-analyzers/blob/main/src/PublicApiAnalyzers/Microsoft.CodeAnalysis.PublicApiAnalyzers.md)) - Helps tracking reusable code public API exposure, aids in proper encapsulation.
* [VSDiagnostics](https://www.nuget.org/packages/VSDiagnostics/) - A collection of code-quality analyzers based on the new Roslyn platform. This project aims to ensure code-quality as you type it in your editor rather than having to do this as a separate build-step.
* [RoslynClrHeapAllocationAnalyzer](https://github.com/mjsabby/RoslynClrHeapAllocationAnalyzer) - Roslyn based C# heap allocation diagnostic analyzer that can detect explicit and many implicit allocations like boxing, display classes a.k.a closures, implicit delegate creations, etc
* [Mews.Analyzers](https://www.nuget.org/packages/Mews.Analyzers/) - Roslyn based code analyzers used by Mews.
* [Blowin.Required](https://github.com/blowin/Blowin.Required/) - Implementation of proposal 'Required Properties' [https://github.com/dotnet/csharplang/issues/3630](https://github.com/dotnet/csharplang/issues/3630).
* [ZeroFormatter.Analyzer](https://www.nuget.org/packages/ZeroFormatter.Analyzer/) - Analyzer of ZeroFormatter, verify rule for [ZeroFormattable] classes.
* [MappingGenerator](https://github.com/cezarypiatek/MappingGenerator) - 🔄 "AutoMapper" like, Roslyn based, code fix provider that allows to generate mapping code in design time.

## Free and online tools

* [Roslyn Quoter](https://github.com/KirillOsenkov/RoslynQuoter) Roslyn tool that for a given C# program shows syntax tree API calls to construct its syntax tree.

## Blogs

* [Fun with Roslyn](https://johnkoerner.com/)
* [Learn Roslyn Now](https://joshvarty.com/learn-roslyn-now/)
