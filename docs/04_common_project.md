
common project

```xml
  <PropertyGroup>

    <Product>MicroElements</Product>
    <Copyright>Alexey Petryashev 2018</Copyright>
    <Authors>alexey.petriashev,MicroElements</Authors>

    <PackageIconUrl>https://raw.githubusercontent.com/micro-elements/MicroElements/master/image/logo_rounded.png</PackageIconUrl>
    <PackageProjectUrl>https://github.com/micro-elements/MicroElements.FileStorage</PackageProjectUrl>
    <PackageLicenseUrl>https://github.com/micro-elements/MicroElements.FileStorage/blob/master/LICENSE</PackageLicenseUrl>
    <RepositoryType>git</RepositoryType>
    <RepositoryUrl>git://github.com/micro-elements/MicroElements.FileStorage</RepositoryUrl>

    <NoWarn>$(NoWarn);1701;1702;1705;CS1591;CS1570</NoWarn>
    <TreatWarningsAsErrors>false</TreatWarningsAsErrors>

    
    <GenerateDocumentationFile>true</GenerateDocumentationFile>
    <DebugType>embedded</DebugType>


    <GenerateAssemblyProductAttribute>false</GenerateAssemblyProductAttribute>
    <GenerateAssemblyCompanyAttribute>false</GenerateAssemblyCompanyAttribute>
    <GenerateNeutralResourcesLanguageAttribute>false</GenerateNeutralResourcesLanguageAttribute>
    <GenerateAssemblyCopyrightAttribute>false</GenerateAssemblyCopyrightAttribute>

    <LangVersion>latest</LangVersion>
    <CodeAnalysisRuleSet>..\..\MicroElements.ruleset</CodeAnalysisRuleSet>
  
  </PropertyGroup>  
```

Directory.Build.props

https://docs.microsoft.com/en-us/visualstudio/msbuild/customize-your-build

https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild-response-files
ключи компиляции

