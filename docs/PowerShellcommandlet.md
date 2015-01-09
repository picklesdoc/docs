# PowerShell commandlet

Pickles comes with a Powershell commandlet that let's you run Pickles from within Visual Studio 2010 and the package manager console. The commandlet is called "Pickle-Features". 

## Getting the commandlet
Installing the commandlet is easy via [Pickles on NuGet.Org](http://nuget.org/packages/Pickles) with the command:

	Install-Package Pickles

## Using the Pickle-Features
Using the commandlet is equally easy by simply go:

	Pickle-Feature

If you then hit tab you get intellisense for the different parameters of the command. 

## Parameters
Listed below are the parameters that you can use with Pickle-Features (in version 0.3.0.0):

* **FeatureDirectory** (Required) - the directory containing the .feature files you want to pickle
* **OutputDirectory** (Required) - the directory where you want the output
* **SystemUnderTestName** (Optional) - the name of the system the features are testing. This will appear in the documentation
* **SystemUnderTestVersion** (Optional) - the version of the system the features are testing. This will appear in the documentation
* **Language** (Optional) - the [language](https://github.com/cucumber/gherkin/blob/master/lib/gherkin/i18n.yml) used in the feature-files.
* **TestResultsFile** (Optional) - the result of a test run using the features. Used to show which test are failing etc. 

## Example - materialistic usage

	Pickle-Features -FeatureDirectory .\Features -OutputDirectory .\Html

## Example - full usage

	Pickle-Features -FeatureDirectory .\Features -OutputDirectory .\Html -SystemUnderTestName ThePickler -SystemUnderTestVersion 1.0.4.1234 -Language sv -TestResultsFile .\TestResults\TestResult20111215.xml
