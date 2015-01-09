# Test Results Format

## Explanation

The format used for the report coming out of the test run o the features.  There are many different testing frameworks supported by SpecFlow, plus all of the other gherkin style frameworks out there.  NUnit and xUnit output formats are accepted as well as output from MsTest.

Output from MsTest.exe is published in a .trx file. VsTest.Console.exe, the new command line runner as of Visual Studio 2012, is also able to produce .trx files, but those are not compatible with Pickles due to missing elements in the .trx file.



**NOTE**: Values are not case-sensitive: i.e. NUNIT = nunit = NUnit

## Default Value

nunit

## Possible Values

nunit, xunit, mstest

## Usage

### Console

	Pickles.exe --test-results-format=xunit

	Pickles.exe -trfmt=xunit

### Powershell

	Pickle-Features -TestResultsFormat xunit

### MSBuild

    <Target Name="document">
        <Pickles ResultsFormat="xunit" />
    </Target>

### NAnt

    <target Name="document">
        <pickles resultsFormat="xunit" />
    </target>
