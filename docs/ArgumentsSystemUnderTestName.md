# System Under Test Name

## Explanation

This is the name of the system under test.  Since Pickles is designed to be used with any platform/language that supports Gherkin feature files we cannot rely on reading in an assembly or a jar file to retrieve metadata about the system under test.  Instead, The user can use this argument to name the system under test.

## Default Value

None.

## Possible Values

Any valid string.

## Usage

### Console

	Pickles.exe --system-under-test-name=MyProject

	Pickles.exe -sn=MyProject

### Powershell

	Pickle-Features -SystemUnderTestName MyProject

### MSBuild

    <Target Name="document">
        <Pickles SystemUnderTestName="MyProject" />
    </Target>

### NAnt

    <target Name="document">
        <pickles systemUnderTestName="MyProject" />
    </target>
