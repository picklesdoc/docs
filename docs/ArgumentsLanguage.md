# Language


## Explanation

Allows the user to tell Pickles the default language of the `.feature` files. Any language settings inside the `.feature` files take precedence.

For more on the concept of languages in `.feature` files, see the [entry on GitHub](https://docs.cucumber.io/gherkin/reference/#spoken-languages).

## Default Value

`en` for English.

## Possible Values

Any of the values defined in the [Gherkin Languages file](https://github.com/cucumber/cucumber/blob/master/gherkin/gherkin-languages.json).

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
