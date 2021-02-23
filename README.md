# Kentico Code Analysis Rule Set

[![Build status](https://ci.appveyor.com/api/projects/status/h17txv85llgocrw0?svg=true)](https://ci.appveyor.com/project/kentico/codeanalysisruleset)

This repository contains a static code analysis rule set used by Kentico projects. The rule set aggregates various code analysis libraries and rules to one reusable NuGet package.

If you're new to static code analysis, take a look at this [video](https://www.youtube.com/watch?v=lFYyp_jUXgs).

:warning: This rule set is designed for Kentico v10. Using the rule set with a previous version of Kentico will produce some additional warnings.

### How do I install the rule set in my projects?

Install this NuGet package as a dependency. This automatically adds references to the code analyzer libraries and downloads the rule set file into the project root folder. 
```powershell
Install-Package Kentico.CodeAnalysis.Ruleset
```
Then, in your project properties > code analysis > select the newly downloaded rule set.

### How do I run code analysis from the command line?

After a successful installation, set the ```RunCodeAnalysis``` parameter in ```MSBuild``` to true and you're good to go.
```powershell
MSBuild MySolution.sln /p:RunCodeAnalysis=true
```

### Benefits of distributing rule set as a NuGet package

- automatic updates of dependencies to Code Analyzer libraries
- automatic updates of the rule set file
- reusability of the same rule set in different projects/solutions

## Active rules

- **Microsoft.AnalyzerPowerPack.Common**
 - :warning: [CA1715](https://msdn.microsoft.com/library/ms182243.aspx): Identifiers should have correct prefix.

