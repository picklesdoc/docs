# Include Experimental Features

## Explanation

As of version 2.5, Pickles includes [experimental features](ExperimentalFeatures.md). The goal of experimental features is to get rapid feedback about ideas. They are subject to change or removal at any time. The experimental features are not always completely thought through - including them and receiving feedback about them enables us to make better decisions about those features.

This argument is a flag. Including the argument means that the experimental features should be included. If the argument is not included, then the experimental features will not be included.

## Usage

### Console

	Pickles.exe --include-experimental-features

	Pickles.exe -exp

### Powershell

	Pickle-Features -IncludeExperimentalFeatures

### MSBuild

    <target Name="document">
        <pickles IncludeExperimentalFeatures="true" />
    </target>

