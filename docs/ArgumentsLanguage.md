# Feature Directory


## Explanation

Allows the user to tell Pickles the default language of the `.feature` files. Any language settings inside the `.feature` files take precedence.

For more on the concept of languages in `.feature` files, see the [entry on GitHub](https://github.com/cucumber/cucumber/wiki/Spoken-languages).

## Default Value

`en` for English.

## Possible Values

Any of the values defined in the [Gherkin Languages file](https://github.com/cucumber/gherkin3/blob/master/gherkin-languages.json).

## Usage

### Console

	Pickles.exe --language=sv

	Pickles.exe -l=sv

### Powershell

	Pickle-Features -Language sv

### MSBuild

    <Target Name="document">
        <Pickles Language="sv" />
    </Target>
