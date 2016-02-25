# Test Results Format

## Explanation

The format used for the report coming out of the test run of the features.  There are many different testing frameworks supported by SpecFlow, plus all of the other gherkin style frameworks out there.  NUnit and xUnit output formats are accepted as well as output from MsTest and SpecRun. As of version 2.4, Pickles also supports output from VsTest.Console.exe, the new command line runner introduced by Visual Studio 2012.

**NOTE**: Values are not case-sensitive: i.e. NUNIT = nunit = NUnit

## Default Value

    nunit

## Possible Values

    nunit, nunit3, xunit, xunit2, mstest, cucumberjson, specrun, vstest

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
