# System Under Test Version

## Explanation

This is the version of the system under test.  Since Pickles is designed to be used with any platform/language that supports Gherkin feature files we cannot rely on reading in an assembly or a jar file to retrieve metadata about the system under test.  Instead, The user can use this argument to set a version number for the system under test.

This argument is typically used in conjunction with a build script on a continuous integration server.

## Default Value

None.

## Possible Values

Any valid string.

## Usage

### Console

	Pickles.exe --system-under-test-version=2.0.1beta

	Pickles.exe -sv=2.0.1beta

### Powershell

	Pickle-Features -SystemUnderTestVersion 2.0.1beta

### MSBuild

    <Target Name="document">
        <Pickles SystemUnderTestVersion="2.0.1beta" />
    </Target>

### NAnt

    <target Name="document">
        <pickles systemUnderTestVersion="2.0.1beta" />
    </target>
