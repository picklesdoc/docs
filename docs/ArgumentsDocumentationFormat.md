# Documentation Format

## Explanation

Allows the user to select what format the generated output will be written in.  Currently, the available options are:

- HTML
- Dhtml
- Word (OpenXML)
- JSON
- Excel
- Cucumber JSON

**Note**: The value passed to this argument is case-insensitive.  i.e. HTML = html= HtMl

**Note**: The Cucumber JSON is used by report generators such as [cucumber-html-reporter | https://www.npmjs.com/package/cucumber-html-reporter] and others to generate test run reports

## Default Value

html

## Possible Values

html, dhtml, excel, json, word, cucumber

## Usage

### Console

	Pickles.exe --documentation-format=Word

	Pickles.exe -df=Word

### Powershell

	Pickle-Features -DocumentationFormat Word

### MSBuild

    <target Name="document">
        <pickles DocumentationFormat="Word" />
    </target>

