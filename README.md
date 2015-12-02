# Kentico Code Analysis Ruleset

[![Build status](https://ci.appveyor.com/api/projects/status/h17txv85llgocrw0?svg=true)](https://ci.appveyor.com/project/kentico/codeanalysisruleset)

This repository contains a static code analysis ruleset used by Kentico projects. The ruleset aggregates various code analysis libraries and rules to one reusable NuGet package.

If you're new to static code analysis, take a look at this [video](https://www.youtube.com/watch?v=lFYyp_jUXgs).

:warning: This ruleset is designed for Kentico v10. Using the ruleset with a previous version of Kentico will produce some additional warnings.

### How do I install the ruleset in my projects?

Install this NuGet package as a dependency. This automatically adds references to the code analyzer libraries and downloads the ruleset file into the project root folder. 
```powershell
# It's recommended to use DependencyVersion to HighestMinor to keep the ruleset automatically updated
Install-Package Kentico.CodeAnalysis.Ruleset -DependencyVersion HighestMinor
```
Then, in your project properties > code analysis > select the newly downloaded ruleset.

### How do I run code analysis from the command line?

After a successful installation, set the ```RunCodeAnalysis``` parameter in ```MSBuild``` to true and you're good to go.
```powershell
MSBuild MySolution.sln /p:RunCodeAnalysis=true
```

### Benefits of distributing ruleset as a NuGet package

- automatic updates of dependencies to Code Analyzer libraries
- automatic updates of the ruleset file
- reusability of the same ruleset in different projects/solutions

## Active rules

- **Microsoft.AnalyzerPowerPack.Common**
 - :warning: [CA1715](https://msdn.microsoft.com/library/ms182243.aspx): Identifiers should have correct prefix.
