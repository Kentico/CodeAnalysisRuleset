# Kentico Code Analysis Ruleset

[![Build status](https://ci.appveyor.com/api/projects/status/h17txv85llgocrw0?svg=true)](https://ci.appveyor.com/project/kentico/codeanalysisruleset)

This repository contains static code analysis ruleset used by Kentico projects. This ruleset aggregates various code analysis libraries and rules to one reusable NuGet package.

If you have no idea what code analysis means, take a look at this [video](https://www.youtube.com/watch?v=lFYyp_jUXgs)

:warning: This ruleset is meant for Kentico v10. In case of use with a previous version, it will produce some extra warnings. 

### How to install ruleset into my project?

Instal this NuGet package as a dependency. It will automatically add references to code analyzer libraries and downloads ruleset file into the project root folder. 
```powershell
# It's recommended to use DependencyVersion to HighestMinor to keep the ruleset automatically updated
Install-Package Kentico.CodeAnalysis.Ruleset -DependencyVersion HighestMinor
```
Then in a project properties > code analysis > select newly downloaded ruleset.

### How to run code analysis from the command line?

After successful installation, add ```RunCodeAnalysis``` parameter into the ```MSBuild``` and you're good to go
```powershell
MSBuild MySolution.sln /p:RunCodeAnalysis=true
```

### Benefits of distributing ruleset as a NuGet package

- automatic updates of dependencies to Code Analyzer libraries
- automatic updates of ruleset file
- reusability of the same ruleset in a different projects/solutions

## Active rules

- **Microsoft.AnalyzerPowerPack.Common**
 - :warning: [CA1715](https://msdn.microsoft.com/library/ms182243.aspx): Identifiers should have correct prefix.
