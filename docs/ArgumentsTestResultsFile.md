# Test Results File

## Explanation

Path to the XML results file. The filename itself can be a wildcard as defined by the [searchpattern of the .NET Directory.GetFiles() method](https://msdn.microsoft.com/en-us/library/wz42302f(v=vs.110).aspx?f=255&mspperror=-2147217396#Anchor_2).

For selecting multiple resultsfiles to be processed, you can use the wildcard searchpattern, you can enter the files as a semicolon separated list or a combination of both. Selecting only a path to a folder will not work, when all files in a folder needs to be selected, append a * to the path.

## Default Value

None.

## Possible Values

Any path(s) or patterns for a results file in XML format as long as it results in at least one match to a valid file. 

## Usage

### Console

	Pickles.exe --link-results-file=C:\MyProject\Reports\results.xml

	Pickles.exe -lr=C:\MyProject\Reports\results.xml
	
	Pickles.exe -lr=C:\MyProject\Reports\*.xml
	
	Pickles.exe -lr=C:\MyProject\UnitTest\results.xml;C:\MyProject\SystemTest\*

### Powershell

	Pickle-Features -TestResultsFile C:\MyProject\Reports\results.xml

### MSBuild

     <Target Name="document">
         <Pickles ResultsFile="C:\MyProject\Reports\results.xml" />
     </Target>
