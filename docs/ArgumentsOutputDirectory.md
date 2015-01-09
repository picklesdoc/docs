# Output Directory

## Explanation

The folder where Pickles will put the generated output.

## Default Value

The current folder.

## Possible Values

Any valid directory path, either absolute or relative.

## Usage

### Console

	Pickles.exe --output-directory=C:\GeneratedDocs

	Pickles.exe -o=C:\GeneratedDocs

### Powershell

	Pickle-Features -OutputDirectory C:\GeneratedDocs

### MSBuild

    <Target Name="document">
        <Pickles OutputDirectory="C:\GeneratedDocs" />
    </Target>

### NAnt

    <target Name="document">
        <pickles output="C:\GeneratedDocs" />
    </target>
