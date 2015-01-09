# Test Results File

## Explanation

Path to the XML results file

## Default Value

None.

## Possible Values

Any path to a valid results file in XML format.

## Usage

### Console

	Pickles.exe --link-results-file=C:\MyProject\Reports\results.xml

	Pickles.exe -lr=C:\MyProject\Reports\results.xml

### Powershell

	Pickle-Features -TestResultsFile C:\MyProject\Reports\results.xml

### MSBuild

     <Target Name="document">
         <Pickles ResultsFile="C:\MyProject\Reports\results.xml" />
     </Target>

### NAnt

     <target name="document">
         <pickles resultsFile="C:\MyProject\Reports\results.xml" />
     </target>
