# Documentation Format

## Explanation

Allows the user to select what format the generated output will be written in.  Currently, the available options are:

- HTML
- Dhtml
- DITA
- Word (OpenXML)
- JSON
- Excel

For more information on the DITA output format, visit [Dita at sourceforge](http://dita-ot.sourceforge.net/).

**Note**: The value passed to this argument is case-insensitive.  i.e. HTML = html= HtMl

## Default Value

html

## Possible Values

html, dhtml, excel, json, word, dita

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

### NAnt

    <Target Name="document">
        <Pickles documentationFormat="Word" />
    </Target>
