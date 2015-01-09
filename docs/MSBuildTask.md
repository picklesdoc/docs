# MSBuild Task

To allow Pickles to integrate right into your build process there is an MSBuild task provided.  You can use this right in your Visual Studio projects or separate MSBuild .proj files.

## Referencing via NuGet
	
The easiest method to install in your project is to use the Pickles.MSBuild NuGet package. This package includes the MSBuild task and a build target that is automatically added to your .csproj.

The default build target is configurable via the following MSBuild properties:

| MSBuild Property               | Description                                                                      | Default
|--------------------------------|----------------------------------------------------------------------------------|-------------------------------------------------------------
| Pickles_Generate               | True or False whether or not to run the build target and generate documentation. | False 
| Pickles_FeatureDirectory       | The path to your project's directory containing SpecFlow features. [See Pickles documentation](ArgumentsFeatureDirectory.md) | $(MSBuildProjectDirectory)\Features 
| Pickles_OutputDirectory        | The Pickles documentation output directory. This directory will be removed if it exists, and recreated. [See Pickles documentation](ArgumentsOutputDirectory.md) | $(MSBuildProjectDirectory)\pickles-site
| Pickles_DocumentationFormat    | [Documentation format](ArgumentsDocumentationFormat.md)                             | [See Pickles documentation](ArgumentsDocumentationFormat.md)
| Pickles_ResultsFormat          | [Results format](ArgumentsTestResultsFormat.md)                                     | [See Pickles documentation](ArgumentsTestResultsFormat.md)
| Pickles_ResultsFile            | [Results file](ArgumentsTestResultsFile.md)                                         | [See Pickles documentation](ArgumentsTestResultsFile.md)
| Pickles_SystemUnderTestName    | [System under test name](ArgumentsSystemUnderTestName.md)                           | [See Pickles documentation](ArgumentsSystemUnderTestName.md) 
| Pickles_SystemUnderTestVersion | [System under test version](ArgumentsSystemUnderTestVersion.md)                     | [See Pickles documentation](ArgumentsSystemUnderTestVersion.md)

#### Example 1 - Configuration via .csproj

One way to control the build target is to add properties to your .csproj file:

    <PropertyGroup>
        <Pickles_Generate>True</Pickles_Generate>
        <Pickles_DocumentationFormat>dhtml</Pickles_DocumentationFormat>
        <Pickles_OutputDirectory>C:\Temp\MyDocumentation</Pickles_OutputDirectory>
    </PropertyGroup>


#### Example 2 - Configuration via MSBuild.exe

Build target properties can also be passed to MSBuild via command-line argument. 

    msbuild /p:Pickles_Generate=True /p:Pickles_DocumentationFormat=dhtml /p:Pickles_OutputDirectory=C:\Temp\MyDocumentation
    



## Manually Referencing the Task

[Download Pickles](/GettingStarted.md) and place the Pickles.MSBuild.Tasks.dll assembly somewhere on your disk (if you are using continuous integration then make sure it is somewhere in your working folder).  You then get access to the Pickles task by including this at the top of your .proj file:

	<UsingTask AssemblyFile=".\path\to\Pickles.MSBuild.Tasks.dll" TaskName="Pickles" />

### Using the Task

The task is very simple to use.  Simply add a target and call the Pickles task from within like so:

    <Target Name="document">
        <MakeDir Directories="$(OutputDirectory)" />
        <Pickles FeatureDirectory="$(FeatureDirectory)" OutputDirectory="$(OutputDirectory)" />
    </Target>

### Sample

See the Pickles.Sample project for an example of using this task in real life.


