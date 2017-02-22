# Exclude a Feature or an Scenario


## Explanation

Allows the user to exclude a Feature or a Scenario by tag.

## Usage

### Console

	Pickles.exe --excludeTags=notInDocumentation

	Pickles.exe -et=notInDocumentation

### Powershell

	Pickle-Features -ExcludeTags notInDocumentation

### MSBuild

    <Target Name="document">
        <Pickles ExcludeTags="notInDocumentation" />
    </Target>
