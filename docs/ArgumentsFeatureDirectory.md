# Feature Directory


## Explanation

Allows the user to tell Pickles the root directory where the feature files are located.  All files underneath this root directory will be added to the output documentation.

## Default Value

None as yet.

## Possible Values

Any valid directory path, either absolute or relative.

## Usage

### Console

	Pickles.exe --feature-directory=C:\MyProject\Features

	Pickles.exe -f=C:\MyProject\Features

### Powershell

	Pickle-Features -FeatureDirectory C:\MyProject\Features

### MSBuild

    <Target Name="document">
        <Pickles FeatureDirectory="C:\MyProject\Features" />
    </Target>

### NAnt

    <target Name="document">
        <pickles FeatureDirectory="C:\MyProject\Features" />
    </target>
