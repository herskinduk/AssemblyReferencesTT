AssemblyReferences.tt
===

What is is?
---

Build target for generating a T4 file with a list of assembly directives based on the projects references. References with a hint path and solution references will be listed the AssemblyReferences.tt file. This file can then be included by other T4 files.

Why would I use it?
---
You may want to automatically generate the assembly directives for your .tt file if you:

* Need to be able to generate code both with Visual Studio and with the TextTransform.exe tool - the latter does not understand build macros like $(SolutionDir)
* Want to distribute a .tt file (e.g. via Nuget) that has dependencies on non-framework assemblies
* Have a .tt file that depends on an assembly that is added to the project via Nuget

How do I use it?
---

1. Install the Nuget package. This adds a build target to the project that generated a fresh list of assembly directives in the file AssemblyReferences.tt
2. In your T4 file add an include directive pointing to the AssemblyReferences.tt file like this:

    <#@ include file="AssemblyReferences.tt" #>

    
Enjoy!

License: MIT
